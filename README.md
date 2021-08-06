### Python API Project - What's the Weather Like?

### Background

Whether financial, political, or social -- data's true power lies in its ability to answer questions definitively. So let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter..."_

But, if pressed, how would you **prove** it?

### Part I 

In this section, I will be creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, I utilize a simple Python library(https://pypi.python.org/pypi/citipy), the OpenWeatherMap API(https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

My first step was to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* ![1](https://user-images.githubusercontent.com/84537717/128538013-adaab480-c2e8-4111-bd7a-f61134a0733f.PNG)

* Humidity (%) vs. Latitude
* ![2](https://user-images.githubusercontent.com/84537717/128538069-bbde6e28-f177-4214-8e40-f7eb35dc8e54.PNG)

* Cloudiness (%) vs. Latitude
* ![3](https://user-images.githubusercontent.com/84537717/128538101-4c223f8b-883b-436c-a0dd-f41691ef7735.PNG)

* Wind Speed (mph) vs. Latitude
* ![4](https://user-images.githubusercontent.com/84537717/128538131-bfc83312-024f-41df-bbca-8d9715cdfb10.PNG)

The second requirement is to run linear regression on each relationship. This time, I separated the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude).  For sake of space in this README, I will only include snapshots of one northern and southern graph:

* Northern Hemisphere - Temperature (F) vs. Latitude
* ![5](https://user-images.githubusercontent.com/84537717/128538307-f0b1242b-eb3c-42ac-b78a-62e3393b7541.PNG)
* Southern Hemisphere - Temperature (F) vs. Latitude
* ![6](https://user-images.githubusercontent.com/84537717/128538392-bf39d1fe-41c5-4dfb-9064-fb36b0c88b61.PNG)
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude


### Part II 

Using jupyter-gmaps and the Google Places API, I created a heat map that displays the humidity for every city from the above section.  I then narrowed down the list to fit my ideal weather conditions (Between 65 and 85 degrees fahrenheit) and used the Google Places API to find the first hotel for each city located within 5000 meters of these coordinates.  Finally, I plotted those hotels on top of a humidity heatmap that also includes the 500+ cities from part 1. 

![heat map](https://user-images.githubusercontent.com/84537717/128538490-ada4c874-9d3b-4b35-8683-3b8e0a370283.PNG)
