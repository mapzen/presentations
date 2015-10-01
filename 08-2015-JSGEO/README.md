# JS.Geo 2015

## Procedural Cartography with Tangram
#### Patricio Gonzalez Vivo
#####Thursday 8, ??:?? PM - 15’ Talks

Hello I’m going to speak about how we procedural generated maps from OpenStreetMaps data.

My name is Patricio Gonzalez Vivo, I’m a new media artist working on the Graphic Engineering team of Mapzen, developing Tangram.

Tangram is our 2D/3D map rendering engine that works on WebGL (on the web) and (openGL ES for native apps). We use all the power of the graphics card to render beautiful maps on the fly from vector tile from OpenStreetMap data.

As an artist I’m one of the responsable of some of the graphics features that this engine supports, like the poly-lines tessellation, materials and lights systems. Materials? lights? Yes, our engine feeds from other inter disciplinary concepts to give more expressive resources. In this case some of the state of the art techniques of the computer graphics world.

I’m talking about the ability of pushing the limits of digital cartography to this kinds of limits:

Go to <http://tangrams.github.io/tangram-sandbox/>

- [From handmade-sketched maps](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/pericoli#17.575/40.70495/-74.00486) [to retro digital onces](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/9845C#10.97291/40.7458/-74.0931)

- [From elegant](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/press#3.82729/20.73/-26.25) [to playfull](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/lego#19/40.70533/-74.00975)


- [From design](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/patterns#17.375/40.70361/-74.01181) [to architectural](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/blueprint#16.575/40.70321/-74.00666)

Or if you like the movies:

-  [From tron](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/tron#16.975/40.70411/-74.00930) [to the matrix](http://tangrams.github.io/tangram-sandbox/tangram.html?styles/matrix#18.4/40.71310/-74.00599)

How this technology works? Let me show you [one of the tools I’m working together with Lou](http://tangrams.github.io/tangram-play/). Hopefully this will show some of the behind the scenes of this Tangram Maps.

This is TangramPlay, our online editing tool for tangram. Here on the right you can see the ```.yaml``` file Tangram use to construct the map.

- Here is the ***```source```*** of the data
- The ***```layers```*** to parse from that data
- And here parameters of how to ***```style```*** this layers.
 
So far up to here, I think looks pretty much as any other template system to raster maps. Right? Here is where start getting interesting. The next properties are more proper from a 3D engine.

- define the ***```camera```***

```yaml
cameras:
    perspective:
        type: perspective
        vanishing_point: [0, -500] 
```

(Change ```camera/perspective/type``` to ```isometric```) 

- the ***```lights```*** of the scene

```yaml
lights:
    directional1:
        type: directional
        direction: [.1, .5, -1]
        diffuse: .7
        ambient: .5
```

(Change ```lights/directional1/diffuse``` to a random color)

But’s this is not the most flexible feature of tangram, language is. Tangram let’s you inject peaces of code into your styles to hijack the main rendering pipe (in real-time). This is done by using ***injections points*** to the shader of each style. ***Language*** is human most versatile tool, let’s us imagine things, define them and share them.
Is through computer graphics languages (in this case GLSL) that the user can change the ***```position```***, ***```width```***, orientation (aka ***```normals```***) and pre-lightening ***```color```*** or post-lightening color (know as ***```filter```***) of anything render in Tangram Maps.

For example let’s se here (back to the default tangramPlay style), buildings have a custom style.

```yaml
styles:
    buildings:
        base: polygons
        shaders:
            blocks:
                color: |
                    color.gb *= vec3(min((v_world_position.z*.001 + .5),1.));
```

In it we are adding a gradient on the sides of the building as they get closer to the ground.

Let’s see what happens when I comment it out (comment/uncomment that line)

On because we believe that this .yaml styles provide great flexibility to our engine, on tangramPlay we didn’t try to hide the code. We are making a ***profesional*** text editor, that gives total and transparent control on the design of the map. We focus our attention to illuminate the experience of using it.

Let me show you an example of this:

- open the [ikeda map](http://tangrams.github.io/tangram-play/?style=https://rawgit.com/tangrams/tangram-sandbox/gh-pages/styles/ikeda.yaml#17.321875000000137/40.70512/-74.01062)

- open the console Alt+Cmd+J

- type on the console:
```
tangramPlay.initAddon(‘sandbox’)
```
- Go to ```styles/roads/shaders/blocks/color```

So while I edit my shaders I can preview them in this little sandbox. Here is something interesting. 

If you pay attention the streets goes in the right direction. How this works?

- Well in this line ```layers``` line:

```yaml
    roads:
        data: { source: ism }
        filter: { not: { highway: service, kind: rail } }
        draw:
            roads:
                order: 5
                color: [0, 0, 0]
                width: 8
            outline:
                style: lines
                order: 4
                color: [0.773,0.763,0.763]
                width: 8.5
        oneway:
            filter: { oneway: yes }
       >>>> draw: { roads: { color: red } } <<<<
```

I’m filtering the oneway roads and assigning them a red color. This is picked up in this line of the shader:

```yaml
    roads:
        base: lines
        mix: tools
        animated: true
        texcoords: true
        shaders:
            blocks:
                global: |
                    float randomSerie(float x, float free, float t) {
                        return step(.8,random( floor(x*freq)-floor(t) ));
                    }
                color: |
                    vec2 st = v_texcoord.xy;
                    float t = 12.*u_time;
                    float freq = 100.;
              >>>>  if ( v_color.r < 0.5) { <<<<
                        float cols = 2.;
                        if (fract(st.x*cols* 0.5) < 0.5){
                            t *= -1.0;
                        }
                    }
                    float offset = 0.025;
                    color.r = randomSerie(st.y, free, t+offset);
                    color.g = randomSerie(st.y, free, t);
                    color.b = randomSerie(st.y, free, t-offset);
                    color.gb *= step(0.1,st.x)-step(0.9,st.x);
```

And change the animation to a different pattern.

The fact the we are using code also provides modularity. Not everybody knows how to write shaders. That’s why I’m working on a library. Right know looks more like a collection of snippets 

<https://github.com/tangrams/tangram-sandbox/tree/gh-pages/modules> 

For example if we want to take this map to the next level we just need to copy and paste:

```yams
    geometry-tilt:
        mix: matrices.yam
        animated: true
        shaders:
            blocks:
                position: |
                    float t = u_time*0.05; 
                    position.xyz = rotateX3D(abs(cos(t))) * rotateZ3D(abs(sin(t))) * position.xyz;
```
<https://github.com/tangrams/tangram-sandbox/blob/gh-pages/modules/geometry/tilt.yaml>

And we can “tilt“ the view of the map:

<http://tangrams.github.io/tangram-play/?style=https://rawgit.com/tangrams/tangram-sandbox/gh-pages/styles/tilt-ikeda.yaml#19.6622916666668/40.70489/-74.00858>

Thank you
