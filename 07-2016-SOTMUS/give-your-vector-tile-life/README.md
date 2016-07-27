### Presentation note

1. Hi, I am Hanbyul Jo. I work as a front-end engineer at Mapzen new York office.
2. I am here to talk about 3D tile exporter.3D tile exporter is a web application which user can preview and download the 3d printable file of selected area.
3. (Live demo) This is how it works.You can search for the location using search box on left top. After the location and the zooml leve are selected,, you can preview the file. In case the result is not exactly what you expected, you canv navigate the area in nine directions . Tile exporter generates obj file, the file is available for download through the link on the left side.
4. This is the result when I printed downloaded file with Makerbot.
5. There are several nice prints from Shapeway. They look really nice with metal materials.
6.
7. This is a fun thing that you can do with tile exporter, if you set zoom level high, you get al-most building itself.
8. In this way I could get al-most empire state building. I had this very specific image in my mind , sipping whiskey with empire state building shaped ice on the  rocks
9. so I put the print in a plastic cup and poured the silicon in it.
10. After silicon hardened, I could get a mold to get ice out of it.
11. Ta dat! I sadly couldn’t take the picture with whiskey because It started melting down right after I poured the whiskey, so sad.
12. What is going on behind of the scene? Everything starts from vector tiles. Vector tiles are squares of math containing the geospatial data instead of pre- baked raster images. Tiles are usually in the format that can be easily used such as topojson and geojson. When a user searches for the location, tile exporter calls geojson vector tile with selected coordinates and zoom level.
13. After getting Geojson from tile server,  Geojson object is converted into SVG (which is shorthand for Scalabe Vector Graphics) by D3 (which is great data visualization library.) The preview maps on right bottoms, those were made in this process, 9 tiles 9 svgs.
14.  Vector tiles have buildings height data. I could  extract the SVG shape based on that height data. Three.js made all of this process very simple. You can see tile exporter is a quite quilt of open source projects!
15. In this process, I found Vector Tiles great for digital fabrication like laser cutter, 3d printer etc. Digital fabrication tools usually expect vector graphics such as SVGs as inputs, because it gotta know the coordinates to move its mechanical arms! Vector tiles are very easy to be converted into vector graphics as I converted tiles into svgs.
16. (Axidraw video) This is another digital fabrication example using vector tiles. SVG was sent to Pen plotter machine, named Axidraw.
17. (Colorful version of Axidraw video)  Vector tile separates different features into its layers, so you can do fun things like giving color to each layer. Actually, Mapzen brought Axidraw to here SOTMUS so you can check it out at Mapzen booth.
18. If you got interested in making something woth vector tiles, you should check out my coworker Karim and Rachel’s projects too. This is way too short talk to talk about how awesome they are.
19. Map has been inspiration for many people’s creativity. and I believe vector tile can inspire even more people in digital fabrication area. I am looking forward to what will come more in near future
20.Thank you ! Here is my Twitter handle, please let me or mapzen know what you are making!