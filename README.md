# World_Weather_Analysis
## Project Overview
The purpose of this project is to update the PlanMyTrip app based of suggestions from Beta testers. With the update, users will be able to see the current weather in addition to latitude and longitude, maximum temperature, percent humidity, percent cloudiness, and wind speed for the randomly selected cities.

Once the information is retrieved, users will be prompted to answer questions in regards to the minmum and maximum temperatures of cities they are looking to visit. The data will be filtered according to their preferences and potential travel destinations and neaby hotels will be identified. 

From the list of potential destinations, the user will choose four (4) cities to create a travel itinerary. Using Google Maps Directions API, a travel route between the four cities as well as a marker layer map will be created. 
## Resources
Data Source: WeatherPy_Database.csv, WeatherPy_Vacatoin.csv, Vacation_Search.ipynb, Vacation_Itinerary.ipynb

Software: Anaconda 4.9.2, Python3.7.9, Jupyter Notebook

## Analysis
First, the weather data had to be retrieved. A set of 2,000 random latitudes and longitudes was created using the below code:

<img width="429" alt="Lat_Lng" src="https://user-images.githubusercontent.com/74752756/107160043-78863800-6959-11eb-8bde-a1bd32f988dc.PNG">

From there, the **citipy** module was used to identify the nearest city. Of the 2,000 latitude/longitude pairs, 760 cities were identified.

The relevant information was retrieved for each city and added to a new DataFrame as shown below.

<img width="458" alt="city_data_df" src="https://user-images.githubusercontent.com/74752756/107160064-918ee900-6959-11eb-8b28-2772c58a1e3c.PNG">


The data was then exported to the Weather_Database folder as a .csv file.

Next, input statements were used to retrieve customer weather preferences. For this testing purpose, the preferences were a minimum temperature of 75 and a maximum temperature of 90. The preferences were used to identify potential travel destinations and nearby hotels. The potential destinations are shown on a marker layer map with pop-up markers. Example shown below.

<img width="671" alt="WeatherPy_vacation_map" src="https://user-images.githubusercontent.com/74752756/107160084-abc8c700-6959-11eb-8c65-819e2c033e48.PNG">

A new DataFrame (hotel_df) was created which used the latitude and longitude of each city to locate the nearest hotel based on search parameters. This DataFrame was also exported as a .csv file and is located in the Vacation_Search folder.

Lastly, Google Directions API was used to create a travel itinerary that shows the route between four cities chosen from the customer's possible travel destinations. Then, a marker layer map with a pop-up marker for each city on the itinerary was created. For this testing purpose, four cities meeting the customer's preferences in Australia were used. Map shown below:

<img width="566" alt="WeatherPy_travel_map_markers" src="https://user-images.githubusercontent.com/74752756/107160126-f21e2600-6959-11eb-9e20-9c31340c4fd0.PNG">

A directions layer map (WeatherPy_travel_map.PNG) and the marker layer map above can be located in the Vacation_Itinerary folder.

## Summary
The list of 760 cities was narrowed down to 162 after the customer input was received. 

Australia was selected to create a vacation itinerary. The four cities selected were Batemans Bay, Flinders, Charlestown, and Moree.
