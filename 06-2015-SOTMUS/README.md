# State of the Map US 2015

## [Mapzen is building Fences… and knocking down barriers](https://github.com/mapzen/presentations/blob/master/06-2015-SOTMUS/BuildingFences.pdf)
#### Diana Shkolnikov
#####Saturday 5:00 PM - Lightning Talks

Mapzen is building Fences… and knocking down barriers! The geo community is well aware of hidden treasures OpenStreetMap data holds. 
One such gem is an astounding collection of polygons representing countries, states, provinces, cities, and so on, also known as 
administrative boundaries, and soon to be known as Fences. Once extracted into a manageable subset and normalized, 
the administrative boundaries from OpenStreetMap could become the go-to source for such data. Fences is a new Mapzen initiative 
to build this dataset from OpenStreetMap and make it publicly available, warts and all. The goal of the Fences project is twofold. 
First, provide the geo community with a viable, trusted, open, and dynamic source for administrative boundary data. 
Second, encourage the community to help improve the underlying OpenStreetMap boundary data by highlighting its inherent value 
as well as its current shortcomings. Mapzen intends to make the Fences dataset publicly available, thereby knocking down 
barriers for those lacking the resources to perform the extraction process internally. In addition, and in true Mapzen fashion, 
all the tools used to generate the Fences dataset will be open-sourced for those wishing to replicate the extraction process 
in-house and contribute to the codebase. Let’s build Fences together.

## [Extracting interesting data from OSM](https://github.com/mapzen/presentations/blob/master/06-2015-SOTMUS/ExtractingInterestingThingsWorkshop-Indy-Diana.pdf)
#### Diana Shkolnikov and Indy Hurt
##### Monday 9:00 AM - Workshops

OSM data is HUGE! Its vastness presents a significant challenge to anyone wanting to extract a meaningful subset of the data. The challenges this presents are twofold. First, how does one figure out what OSM contains that might be of interest. Second, how does one go about extracting that awesome, meaningful, super important data.

This workshop will walk participants through browsing OSM data using taginfo to identify potentially interesting items. Once a meaningful subset of the data has been targeted, the focus will switch to extracting that data. Various available tools will be examined, such as osmfilter, osmium, fences, etc. The group will perform a simple polygon extraction using fences, which is an administrative boundary extraction tool for OSM.

Finally, the participants will work on a simple visualization of the shiny new extracted data. Participants should walk away with a good grasp on some simple and powerful tools for working with OSM data to create and visualize their own custom datasets.

## [Peripheral Data in OpenStreetMap](PeripheralDataInOpenStreetMap.pdf)

#### panel moderated by Drew Dara-Abrams

OpenStreetMap is a giant datastore, with an extremely flexible data model. Its API accepts all additions. But, in fact, not everything belongs or fits in OpenStreetMap.

Some thematic data require more advanced modeling than OpenStreetMap’s simple tagging scheme supports. To represent a building in full 3D requires a data model that supports solids, and to represent a public transit network or traffic patterns requires a data model that handles space and time.

Other types of data come from authoritative sources and may require cleaning, combining, and perhaps even legal review before they’re ready to be added to OpenStreetMap. For example, street addresses and trailheads.

Just as not every kind of data can fit into OpenStreetMap, not every kind of data can easily be extracted from OpenStreetMap. Storing data outside of OpenStreetMap proper may also make that data more relevant to other users’ needs. For example, supporting data consumption in mobile apps, or supporting data collection with topic specific editor apps.

We’ll discuss peripheral data to OSM, both in terms of technical implementation and in terms of community impacts. If done well, data projects that are connected but not subsumed by OSM can advance open geo data. Let’s figure out together how that’s best done.

Panelists:

- Ian Dees, [OpenAddresses](http://openaddresses.io/)
- Jan Erik Solem, [Mapillary](http://www.mapillary.com/)
- Jereme Monteau, [OpenTrails](http://www.opentraildata.org/)
- Drew Dara Abrams, [Transitland](https://transit.land)
- Diana Shkolnikov, [Borders](https://mapzen.com/data/borders)

## [DIY GPS devices](https://github.com/mapzen/presentations/blob/master/06-2015-SOTMUS/DIY-GPS.pdf)
#### Patricio Gonzalez Vivo
#####Sunday 3:00 PM - Lightning Talks

Hello, I’m Patricio Gonzalez Vivo.
One year ago I was scrapping google street views database and constructing landscapes with it. But this data was private. On August I join Mapzen, and start experimenting with openData, open street maps data, and using computer graphics technology, to push forward how maps can look like … (slides)

Today I want to talk not about beautiful maps, but more about the opposite. Because true openness also means giving access to a wither audience. 
I use our native render, on a in-expensive and slow device. This little device designed to be use on school and cost lest than 35 dollars, runs a full linux distribution. The perfect host for openData and openSource. Together with a GPS module, a touch screen and a battery, holder together with a 3D printed core I made this device portable. Then was the challenge of the Graphic User Interface. The screen is not multi-touch. You can only interact with one finger. 
I add this two scroll areas for the rotation and zoom together with a button for updating the location

Here how it looks. (images)

I hope this DIY GPS can be the starting point and inspiration for mappers, makers, hobbies or students that enjoy making their own tools. 

Here you can learn more about this project and find new and exciting ways of using it.

* http://github.com/tangrams/PI-GPS
* https://mapzen.com/blog/raspberrypi-gps-at-sotmus

Thank you