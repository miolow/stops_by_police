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
(slides_pics/Slide2.png)
