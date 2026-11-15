# Identifying the Impacts of Texas' Winter 2021 Storm


## Purpose of this Repository
This repository is for Homework 4 for EDS 223: Geospatial Analysis & Remote Sensing. The analysis studies the major power crisis that Texas suffered in February 2021 after a series of three severe winter storms that happened on February 10-11, 13-17, and 15-20. We identify the impacts these storms had on the Houston metropolitan area. The outputs are a set of maps comparing night light intensities before and after the first two storms, an estimate of the number of homes in Houston that lost power, and a map of these homes. 


## Package Dependencies
* `tidyverse`
* `sf`
* `terra`
* `tmap`
* `stars`


## File Structure
```
.
├── data
│   ├── gis_osm_buildings_a_free_1.gpkg
│   ├── gis_osm_roads_free_1.gpkg
│   └── VNP46A1
│       ├── VNP46A1.A2021038.h08v05.001.2021039064328.tif
│       ├── VNP46A1.A2021038.h08v06.001.2021039064329.tif
│       ├── VNP46A1.A2021047.h08v05.001.2021048091106.tif
│       └── VNP46A1.A2021047.h08v06.001.2021048091105.tif
├── README.md
└── texas-winter-power-outages.qmd
```

## Data Information & Access

**Night Lights**

NASA's Worldview was used to explore the data around the day of the storm. There are several days with too much cloud cover to be useful, but 2021-02-07 and 2021-02-16 provide two clear, contrasting images to visualize the extent of the power outage in Texas. 

Visible Infrared Imaging Radiometer Suite (VIIRS) data is distributed through NASA's [Level-1 and Atmospheric Archive & Distribution System Distributed Active Archive Center (LAADS DAAC)](https://ladsweb.modaps.eosdis.nasa.gov/).

To prevent this assignment from being a large data wrangling challenge, the following files were downloaded and preppe and are stored in the `VNP46A1` folder.

Data files:
* `VNP46A1.A2021038.h08v05.001.2021039064328.tif`: tile h08v05, collected on 2021-02-07
* `VNP46A1.A2021038.h08v06.001.2021039064329.tif`: tile h08v06, collected on 2021-02-07
* `VNP46A1.A2021047.h08v05.001.2021048091106.tif`: tile h08v05, collected on 2021-02-16
* `VNP46A1.A2021047.h08v06.001.2021048091105.tif`: tile h08v06, collected on 2021-02-16


**Roads**

Highways typically account for a large portion of the night lights observable from space. To minimize falsely identifying areas with reduced traffic as areas without power, we will ignore areas near highways.

[OpenStreetMap (OSM)](https://planet.openstreetmap.org/) is a collaborative project which creates publicly available geographic data of the world. Ingesting this data into a database where it can be subsetted and processed is a large undertaking. Fortunately, third party companies redistribute OSM data. We used [Geofabrik’s download sites](https://download.geofabrik.de/) to retrieve a shapefile of all highways in Texas and prepared a Geopackage (.gpkg file) containing just the subset of roads that intersect the Houston metropolitan area. 

Data file:
* `gis_osm_roads_free_1.gpkg`



**Houses**

OpenStreetMap also contains building data. We again downloaded from Geofabrick and prepared a GeoPackage containing only houses in the Houston metropolitan area.

Data file: 
* `gis_osm_buildings_a_free_1.gpkg`



## Authors
Author: [Karolina Sienko](https://github.com/karolinasienko)
Contributor: [Annie Adams](https://github.com/annieradams)


## Citations

Geofabrik. (n.d.). US South [OpenStreetMap data extract]. Retrieved November 12, 2026, from https://download.geofabrik.de/north-america/us-south.html


