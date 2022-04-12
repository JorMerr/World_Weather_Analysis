# World_Weather_Analysis

## Overview of Project

The purpose of this project is to create a vacation itinerary using Google APIs and OpenWeather API.


### Process to Generate Itinerary

#### Gather Weather Information

The first section of the project involved generating random sets of latitude and longitude pairs and using the CitiPy module to locate the nearest cities to the pairs. 

Next, using the cities, we used the OpenWeather API to collect information in JSON format for City Name, Country, Latitude, Longitude, Max Temperature, Humidity, Cloudiness, Wind Speed, and Current Weather Description.

This data was then used to create a DataFrame, and then exported as CSV file within the Weather_Database folder.

#### Gather Hotel Information

The second section of the project involved using the previously generated Weather Data to locate the nearest Hotel to Preferred Cities using Google API. First, the user is asked what their minimum and maximum temperature preference would be for their trip. For this project, the minimum temperature was set at 75°F, and the maximum temperature was set at 90°F.

A new DataFrame was created for the cities which met the preferred temperature range. This DataFrame was then cleaned of any missing values which may not have been collected from the OpenWeather API search.

Next, using Google API, we iterated through the preferred cities DataFrame to find the first Hotel Name from the results of hotels near the Latitude and Longitude of each city. Each Hotel Name was added to the Hotel Name column of a new DataFrame.

The Hotel DataFrame was cleaned of any missing values for Hotel Names that were not located, and was then exported as a CSV file to the Vacation_Search folder. A map image was generated with the hotel locations as markers on the map, with an Info Box which appears when the location marker is clicked to review data for each Hotel in each City. An image of the Hotel marker map was save to the Vacation_Search folder.

![Hotels Map](https://github.com/JorMerr/World_Weather_Analysis/blob/main/Vacation_Search/WeatherPy_vacation_map.png)

#### Plan Trip Itinerary

The final section of the project involved using Google API to map a Trip Itinerary between 4 different cities. For the purposes of this project, 4 cities were chosen in Mexico, all of which met the temperature range criteria, and all of which could be travelled between by Driving.

![Driving Map](https://github.com/JorMerr/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map.PNG)

First, the preferred cities CSV file was used to generatea DataFrame of cities which met the original temperature range criteria. We then repurposed our code from the location markers map image to generate the image again and search for suitable cities in a single country between which travel by car was available. The cities chosen were all in Mexico; Lazaro Cardenas; La Cruz; Chicontepec; Anton Lizardo. The start and end cities for the trip were both Lazaro Cardenas.

A new image was created using Google Directions API to set a Directions Layer with the Start and End Points, the Waypoints of the three other cities to visit, and the Travel Mode of Driving. The image with the Info Boxes for the Hotel and City information was saved to the Vacation_Itinerary folder.

![Hotel Info](https://github.com/JorMerr/World_Weather_Analysis/blob/main/Vacation_Itinerary/WeatherPy_travel_map_markers.PNG)