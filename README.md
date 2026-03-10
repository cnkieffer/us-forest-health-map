# US Forest Health Map

### By Dr. Christina Kieffer


## Project Description

This project visualizes forest cover across the contiguous United States to explore spatial patterns in forest health and potential restoration needs. The map displays the percentage of forest cover across states and counties from 2020–2024.

Forest cover data were derived from the Annual National Land Cover Database (NLCD) provided by the Multi‑Resolution Land Characteristics Consortium. The dataset is generated from remotely sensed Landsat satellite imagery and provides classified land cover data across the United States.

Users can interactively explore forest cover by:

•	Switching between state-level and county-level summaries
•	Selecting different years between 2020 and 2024

The purpose of this map is to provide an accessible visualization that helps highlight areas where forest cover is lower and where forest restoration efforts may be most needed.

Note: This project focuses only on forest ecosystems and does not include other ecosystem types within the United States.

## How to Use the Map

1. Use the Select Indicator dropdown to switch between:

•	States – view forest cover summarized by state
•	Counties – view forest cover summarized by county

2. Use the Select Year dropdown to change the year displayed on the map.

3. Click on any state or county to open a popup showing the percent forest cover.

4. Click the Map Info button to open the sidebar with additional information about the project.


## Data Sources

Forest land cover data were obtained from:

https://www.mrlc.gov/data

The Annual National Land Cover Database (NLCD) provides land cover classification derived from Landsat satellite imagery and includes multiple land cover classes across the United States.

For this project, forest cover was derived from the following NLCD classes:

•	41 – Deciduous Forest
•	42 – Evergreen Forest
•	43 – Mixed Forest

## Methodology

### Data Processing:

1. Land cover data from 2020–2024 were downloaded from the MRLC website.

2. Forest cover was extracted by selecting the three NLCD forest classes:

•	Deciduous forest
•	Evergreen forest
•	Mixed forest

3. These classes were isolated in QGIS using raster reclassification:

(("landcover@1" = 41) OR
 ("landcover@1" = 42) OR
 ("landcover@1" = 43)) * 1

4. Zonal statistics were calculated for both states and counties to determine the number of forest pixels within each boundary.

5. Percent forest cover was calculated in the attribute table using:

("sum" / "count") * 100

6. Final datasets were exported as GeoJSON files for use in the web map.

## Map Objectives

The goals of this project are to:

•	Visualize spatial patterns of forest cover across the United States
•	Allow users to explore forest cover by year
•	Allow users to switch between state and county spatial scales
•	Provide an interactive tool that can help identify regions where forest restoration may be beneficial

## Thematic Representation

The map uses a choropleth visualization to represent percent forest cover.

Darker green colors indicate higher forest cover, while lighter colors represent lower forest cover.

Additional interactive features include:

•	Map popups displaying forest cover values
•	Dropdown menus for selecting year and spatial scale
•	Sidebar panel providing project information
•	Zoom and pan controls for navigation

## Technology Stack

The project uses the following tools and technologies:

•	Leaflet.js – interactive web mapping library
•	CartoDB Dark Matter basemap – background map tiles
•	GeoJSON – spatial data format used for map layers
•	QGIS – spatial analysis and raster processing
•	GitHub Pages – hosting the interactive map

## Repository Structure

US-Forest-Health-Map/
│
├── index.html
├── README.md
├── Data/
│   ├── Forest_Percent_State_2020.geojson
│   ├── Forest_Percent_State_2021.geojson
│   ├── Forest_Percent_State_2022.geojson
│   ├── Forest_Percent_State_2023.geojson
│   ├── Forest_Percent_State_2024.geojson
│   ├── Forest_Percent_County_2020.geojson
│   ├── Forest_Percent_County_2021.geojson
│   ├── Forest_Percent_County_2022.geojson
│   ├── Forest_Percent_County_2023.geojson
│   └── Forest_Percent_County_2024.geojson


## Limitations

•	Forest health is approximated using percent forest cover, which does not capture all ecological stressors such as pests, drought, wildfire, or disease.
•	The dataset is derived from satellite imagery, which may include classification uncertainty.
•	Aggregating data to state and county boundaries may mask fine-scale variation in forest conditions.

## Future Improvements

Potential improvements for this project include:

•	Adding time-series visualization to show forest cover change over time
•	Integrating wildfire and disturbance datasets
•	Adding charts summarizing forest cover trends
•	Improving mobile responsiveness

## Hosting

The interactive map is hosted using GitHub Pages.

## Links

GitHub Repository
https://github.com/cnkieffer

Interactive Map
https://cnkieffer.github.io/us-forest-health-map/
