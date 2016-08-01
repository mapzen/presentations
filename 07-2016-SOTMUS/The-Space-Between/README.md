#### State of the Map US 2016
## Representing streets in OpenStreetMap with curblines

### Overview

My talk is about representing streets in OpenStreetMap with curblines instead of centerlines at higher zoom levels.

At lower zoom levels, street centerlines provide an overview of the connectivity and hierarchy of the road network and are appropriate for optimizing transportation across physical space. But centerlines are visually awkward at higher zooms, especially in urban settings where understanding the volume of the space between objects within it (like trees and benches) is critical.

Mapping fine-grained details in OpenStreetMap is challenging because open data not evenly availability nor is there as many mappers that can commit to such micro-mapping tasks. However, one first step we can take is to adopt municipal planimetric data, such as curblines. These edges between asphalt and sidewalk space indicate regions of automobile traffic space versus pedestrian-friendly public space. Visualizing curblines creates a different sense of space, improves OpenStreetMap adoption by urban planners, and sets up a launching pad for further mapping within the community. In this overview, I will focus on Philadelphia, but also look at quality and licensing of existing data sources around the world, and finally address visual integration of this data in map rendering engines such as Mapzen’s Tangram.

### Links from the presentation

- OpenStreetMap Wiki - Street area proposed feature - http://wiki.openstreetmap.org/wiki/Proposed_features/Street_area
- OpenDataPhilly Curbs dataset - https://www.opendataphilly.org/dataset/curb-edges
- Tangram prototype with Philly data (demo) - http://tangrams.github.io/curblines/ (Warning: this loads slowly)
- Tangram prototype with Philly data (code) - https://github.com/tangrams/curblines/
- The Space Between - meta repo / wiki - https://github.com/mapzen/the-space-between/
- The Space Between - Curb edges data sources - http://bit.ly/curblines

### Contact

Twitter: [@saikofish](https://twitter.com/saikofish)
E-mail: lou@mapzen.com


