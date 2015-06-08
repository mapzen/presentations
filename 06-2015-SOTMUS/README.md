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
