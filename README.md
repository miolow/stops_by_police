# Stops by Police (A GIS Project)

## Project Overview
This project incorporates law enforcement data along with US Census and American Community Survey data and allows for the examination of disparities in encounters with the police. The project features various techniques. First, it pulls in US Census data and then implements areal interpretation to get population estimates of the various neighborhoods of the city. Next, using the addresses of each stop with law enforcement, I identified the latitudes and longitudes for more precise analyses. The third component is creating a disparity index for each neighborhood (while taking neighborhood racial population into account); it informs us of the disparity experienced by Black drivers compared to White drivers. Finally, the results are presented in the form of a map.

## Features
- Pulls in data from US Census and American Community Survey
- Cleans and structure address data along with using Google Maps API and geopy to identify latitudes and longitudes of each stop
- Creates disparity index to examine for differences in law enforcement encounters for Black and White drivers
- Presents the disparity index of each neighborhood in a map

## Tech Stack
The following libraries and tools were used:
- Pandas
- Numpy
- Geopandas
- Shapely
- Matplotlib
- Google Maps API
- Geopy

## A Closer Look 
### Context
In many American neighborhoods, a routine traffic stop can reflect more than a broken tail-light or a speeding ticket. It can expose patterns of racial disparity in policing. In this project, we ask the question, are Black drivers getting stopped more so than White drivers? A variety of data and techniques were employed to examine this question.
![Question](slides_pics/Slide2.PNG)

### Methods and Data
To examine this question, data from different sources needed to be pulled and appended together. First, law enforcement data was cleaned and structured so that the stop associated with each address will have an accompanying latitude and longitude. Next, law enforcement data was combined with the official shapefiles, thereby letting us identify which neighborhood did each stops occur in. 

![Data](slides_pics/Slide4.PNG)

Meanwhile, demographic details such as population of each neighborhood and racial population makeup of each neighborhood is pulled from the Census. However, this data was only formatted in the form of census tract and not each neighborhood. To resolve this, I conducted areal interpolation, a method used to estimate data from one set of geographic zone to another set. In this case, I was estimating the demographic values of each neighborhood from census tract since I did not have access to neighborhood population data. For example, in attempting to figure out the demographic details of Neighborhood J, I take the proportion of census tract A that overlaps in Neighborhood J and combined it with the proportion of census tract C (80%), census tract D (94%), and census tract E (55%) that also overlapped in Neighborhood J. The combination of these tract's proportions are then used as the estimates for the neighborhood's demographic estimates. 

<div style="display: flex; justify-content: center; gap: 10px;">
  <img src="slides_pics/Slide5.PNG" alt="Areal1" width="200" />
  <img src="slides_pics/Slide6.PNG" alt="Areal2" width="200" />
  <img src="slides_pics/Slide7.PNG" alt="Areal3" width="200" />
</div>
<div style="display: flex; justify-content: center; gap: 10px; margin-top: 10px;">
  <img src="slides_pics/Slide8.PNG" alt="Areal4" width="200" />
  <img src="slides_pics/Slide9.PNG" alt="Areal5" width="200" />
</div>
