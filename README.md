# US Forest Health Map

### By Dr. Christina Kieffer


## Project Descript:

For this project I would like to focus on the current health of US forests. The purpose is to help foresters and stackholders determine what areas have the greatest restoration needs. THis will be done by looking at the percent forest cover throughout the low 48 US states over 5 years from 2020-2024. This map can be displayed viewing forest cover percent over the state or within a county. 

Users should note this map only cover forest ecosystems and does not include other ecosystem types within the United States. 


## Data Sources:

https://www.mrlc.gov/data

## Methodology:

### Data Processing:

1.	I downloaded data from 2020-2025 from https://www.mrlc.gov/data. The Multi-Resolution Land Characteristics Consortium provides data for the Annual National Land Cover Database. The data is from remotely sensed Landsat data and provides different land cover types. I focused primarily on forest cover across the lower 48 US states. The files were in geojson files.

2.	I then identified three classes in my raster for forest type of deciduous forest, evergreen forest, and mixed forest. I then reclassified the raster to just show those forests.
(("landcover@1" = 41) OR
 ("landcover@1" = 42) OR
 ("landcover@1" = 43)) * 1

3.	The next step was to calculate zonal statistics found in each state and in each county.

4.	I then calculated percent forest cover in the attribute table for both state and county.
("sum" / "count") * 100

5.	I then exported those files as geojson to be used in the final project.


## Map Objectives:

•	Visualize spatial patterns of forest health and disturbance across the U.S.
•	Allow users to explore different years and at state and county level. 
•	Allow users to visualize percent forest cover across the U.S. and help support locating restoration needs.


Thematic Representation Methods:
•	Choropleth maps to show forest cover, landcover change, or disturbance intensity by county or state.
•	Point or proportional symbol maps for invasive species occurrences or hazardous sites.
•	Layer toggles to compare different forest stressors.
•	Time-based visualizations where applicable (e.g., landcover estimates across years and/or change in temperature).

User Interface (UI):
•	Interactive map with zoom and pan.
•	Dropdown or toggle controls to switch between forest health indicators.
•	Tooltips providing detailed information for individual features (e.g., site name, year, severity).
•	Optional linked charts to summarize trends or totals by region.
•	Responsive layout suitable for desktop viewing.

## Wireframes:

•	A main map panel displaying forest health data.
•	A side panel for controls and charts.
•	UI elements for filtering by variable or time period.

## Data Processing:

•	Use of QGIS where needed.
•	Data formats were GeoJson.

Technology Stack:
•	Leaflet.js – for interactive mapping
•	Leaflet Choropleth or D3 (if needed) – for thematic styling
•	Papa Parse – if reading CSV data
•	Bootstrap – for layout and UI
•	GitHub Pages – for hosting

## Hosting:

•	Hosting will be done on GitHub pages for the final map.
