# India Wasteland Atlas Data + Visualizations 
This is a final project for the Geographical Information Sciences minor at the University of Chicago. 

### Goals and Objectives
This project aims to make current India Wasteland data and visualization available to potential researchers. The project was motivated by the relative inaccessibility of the Indian Wasteland Atlas data, as the maps were not interactive and were only available to readers in over 30 separate PDFs, with no central, accessible repository for data. Below you will also see explanations and visuals of the process, visualizations of the Indian Wasteland Atlas Data for 2008 and 2015, and a link to an interactive RMarkdown map. 

## Motivation
Wasteland is an interesting classification in India, which roots dating back to the British Raj and has been shown by geography professor Jennifer Baka (2013, 2017) to not only be connected to colonial notions of land and worth in India, but was intimately connected to eminent domain, and the separation of land from communal purposes and Adivasi (tribal) and Dalit people. Baka examines how the rural state of Tamil Nadu has made it an overarching priority to eliminate wastelands and increase the production of biofuel, leading to policies that helped facilitate local corruption that led to a vast amount of land grabs from poor, rural farmers. Baka also pointed to the importance of seeing wasteland change in the larger context of the World Bank's promotion of unused land, which led to what has been termed a global land grab. This makes the percent changes in wasteland seen in India from 2008-2015, particularly of interest, because they may point to specific development practices on the state-by-state and district-by-district level.

### Data
The reports I am using for this project were published in September 2019 and include 23 categories of wasteland, which run the gamut from waterlogged land to areas of shifting cultivation to industrial wastelands to glacial areas. The data was made available from India's Department of Land Resources (based in New Delhi) and the National Remote Sensing Centre (based in Hyderabad).

Overall, this data source found wastelands to be 16.96 percent of the land in India in 2016-16 (557,665.51 sq km), down from 17.22 percent in 2008-9 (566,070.36 sq km). The report sees the reduction of wasteland areas being most observed in areas with dense scrub, marshy areas, degraded pastures, and ravenous land. This points to areas that were deemed as hard to cultivate or use for "productive" economic purposes being converted into "usable" land (xxvii).

This mapping project uses data compiled and cleaned from the India Wasteland Atlas' 2019 report. Therefore, these maps include certain idiosyncrasies of the document, for instance in the state of Jharkhand, the 2019 Wasteland Atlas does not include data for the districts of Khunti and Ramgarh. Also, for five Indian states: Assam, Haryana, Kerala, Rajasthan, and Uttarakhand, there is only state-wide data currently available for public use. Broadly, there is no commercial shapefile (I could find) that included the exact district boundaries used in the 2019 report, where, for instance, Telangana's districts reflect the state right after independence, rather than the additional districts recognized in 2023. In order to accommodate, I created a custom shapefile, which the next section details.

## Overview of Process
In order to create a shapefile that best fit the districts and their boundaries in the 2019 wasteland report, I imported two different shapefiles, one created by Princeton and the other by Stanford (visualized below), standardized the tables in R, and used QGIS to merge the shapefiles and further edit their geometries by dissolving boundaries and renaming districts. In the combined shapefile I also used a state shapefile for the states for which there is no district information publically available. 

<img width="820" alt="Shapefiles Used to Create Custom Shapefile" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/d0a4415b-0dd9-4396-9198-aa95ffe3424c">

<img width="783" alt="Custom Shapefile" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/9680d3f2-536f-4d74-98b6-64ac000ec98c">

<img width="783" alt="Custom Shapefile Used For Geocoding Data" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/bbea6fe0-f42a-4de3-8ba3-066d6bf2eb9a">

## Static Maps
<img width="1031" alt="Map of Percent of Indian Wasteland in 2008 (left) and 2015 (right)" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/0fe2ffa0-f965-4542-9372-bd7d75c89df8">

<img width="798" alt="Map of Percent Difference in Indian Wasteland, 2008 to 2015" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/b1150da4-04e1-4491-ac8c-e4bde7139636">

## Screen Shot of Dynamic Map Created by RMarkdown File
<img width="999" alt="Screen Shot of Dynamic Map in RMarkdown" src="https://github.com/ezazy/IndiaWasteland/assets/79418915/73e8c3b8-2dea-4541-ac11-fa96b14998af">

 (in order to create this on your setup, customize the import of the WastelandGeo file to your R home directory)

## Sources 

Geospatial
* https://geodata.lib.utexas.edu/?f%5Bdc_format_s%5D%5B%5D=Shapefile&f%5Bdct_spatial_sm%5D%5B%5D=India&f%5Blayer_geom_type_s%5D%5B%5D=Polygon&per_page=100
* https://earthworks.stanford.edu/?_=1462045970854&f%5Bdc_format_s%5D%5B%5D=Shapefile&f%5Bdc_subject_sm%5D%5B%5D=Boundaries&f%5Bdct_spatial_sm%5D%5B%5D=India&per_page=100&sort=dc_publisher_sort+asc%2C+dc_title_sort+asc

Indian Wasteland Atlas
* https://dolr.gov.in/en/documents/wasteland-atlas-of-india

For further information on Wasteland in India see:
* Baka, Jennifer. “The Political Construction of Wasteland: Governmentality, Land Acquisition and Social Inequality in South India.” Development and Change, vol. 44, no. 2, 2013, pp. 409–428., https://doi.org/10.1111/dech.12018. 
* Baka, Jennifer. "What wastelands? A critique of biofuel policy discourse in South India." 2014, Geoforum 54:315–323



