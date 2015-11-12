# MaptimeOAK: Geocoding and place search edition

Welcome to [MaptimeOAK on geocoding and place search](http://www.meetup.com/Maptime-SF/events/226540295/)

12 November 2015

Rhonda Glennon
([Mapzen](https://mapzen.com/), `@rmglennon`)

Geocoding turns addresses and place names into geographic coordinates for mapping. Geocoding is one of the essential tools you need to put points on maps and power routing and navigation. When you type in an address or landmark in to your phone, a geocoding process converts those words into coordinates and displays the search result on your map.

## Agenda

- Welcome and introductions
- Get ready for the tutorial: install a text editor
- Basics of geocoding
- Examples of geocoding and discussion on how you are using it
- Tools you can use for batch geocoding
- Hands-on tutorial: Add Mapzen Search box to a Leaflet map (most of tonight is here)

## Get ready for the tutorial

To work through the tutorial, you need a text editor, an Internet connection, and a modern browser. All the source code is provided for you.

While you can use the text editor apps installed with your operating system, such as Notepad or TextEdit, they do not provide the helpful indentations, code coloring and autocomplete, or text alignment options found in the other editors.

Example text editors:

- [Atom - OS X, Windows, Linux](https://atom.io/)
- [Notepad++ - Windows](https://notepad-plus-plus.org/)
- [TextWrangler - OS X](http://www.barebones.com/products/textwrangler/)
- [Sublime - OS X, Windows, Linux; free trial](http://www.sublimetext.com/).

For TextEdit, you must go to the Format menu and click Make Plain Text to use the plain-text version of the file. Do not use an app that applies rich formatting, such as Word or Wordpad.

## Basics and definitions

- geocoding - converting an address or the name of a landmark or business into a latitude, longitude pair. Sometimes referred to as forward geocoding.
- reverse geocoding - converting a latitude, longitude pair into the name and address of the nearest place.
- batch geocoding - performing geocoding processes in bulk, commonly by converting a spreadsheet of addresses into points on a map.

## Examples of geocoding

- Search boxes on a map
- Address search boxes for hotels
- Autocomplete for addresses on an order form
- Suggestions for meeting locations on a calendar
- Routing between locations
- Tap a location on a map and get the business name or address (reverse geocoding)

## Turn a list of addresses into points on a map (batch geocoding)

If you have a spreadsheet of addresses or other location attributes that you want to draw on a map, you can use batch geocoding to put the points on a map in bulk. For example, you might want to map census or population data, environmental monitoring or hazard locations, restaurant health inspection lists, buildings available for rent, and so on. There are many tools available to do this, with some having generous free limits; here are a few of them.

- [CartoDB Academy and free accounts](https://cartodb.com/signup?plan=academy) - geocoding credits and free storage space
- [csvgeocode](https://github.com/veltman/csvgeocode) - geocode a CSV into [Google](https://developers.google.com/maps/documentation/geocoding/), [Mapbox](https://www.mapbox.com/developers/api/geocoding/), [OSM Nominatim](http://nominatim.openstreetmap.org/), [Mapzen](https://mapzen.com/projects/search), and [Texas A & M's](http://geoservices.tamu.edu/Services/Geocode/WebService/) geocoders.
- [Geocodio](http://geocod.io/) - geocoding service
- [Google Fusion Tables](http://mappingmashups.net/2012/11/29/mapping-with-google-fusion-tables/) - tutorial from Maptime
- [Esri ArcGIS Online](http://www.arcgis.com/home/webmap/viewer.html) - can geocode about 250 points with a free/public account

## Hands-on tutorial with Mapzen Search

[Mapzen Search](https://mapzen.com/projects/search) is a modern, geographic search service based entirely on open-source tools and open data. You will learn how to make a map with a search box that allows you to enter addresses and place names and locate them on a map. By the end of the night, everyone will have built a searchable web map!

Follow along with the group, or work ahead on your own.

Walkthrough instructions: https://github.com/pelias/pelias-doc/blob/master/add-search-to-a-map.md
