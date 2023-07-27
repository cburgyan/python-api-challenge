# python-api-challenge
This project had two parts. Part 1 was to see if it could be shown that the temperature gets hotter on average as one approaches the equator (i.e. that the temperature increases on average as the magnitude of latitude decreases). Part 2 asks from the cities collected in part 1, what cities have weather that matches an ideal vacation spot along with a hotel that one could stay at.

### Part 1
In part 1, approximately 500 latitude and longitude pairs were randomly generated and citipy was used to find the nearest city to that pair. Then a weather dataframe was created with the 500+ cities by requesting weather for each city from openweathermap.org where the columns that were included were:

1. City
2. Latitude
3. Longitude
4. Maximum Temperature
5. Humidity
6. Cloudiness
7. Wind Speed
8. Country
9. Date

Then matplotlib was used to create the following plots from the weather dataframe:

1. Latitude vs. Maximum Temperature
2. Latitude vs. Humidity
3. Latitude vs. Cloudiness
4. Latitude vs. Wind Speed
5. Northern Hemisphere: Maximum Temperature vs. Latitude
6. Southern Hemisphere: Maximum Temperature vs. Latitude
7. Northern Hemisphere: Humidity vs. Latitude
8. Southern Hemisphere: Humidity vs. Latitude
9. Northern Hemisphere: Cloudiness vs. Latitude
10. Southern Hemisphere: Cloudiness vs. Latitude
11. Northern Hemisphere: Wind Speed vs. Latitude
12. Southern Hemisphere: Wind Speed vs. Latitude

Using Scipy.stats a Pearson's R coefficient and a linear regression were included in the plots 5 - 12 to show if general linear trends were present in the dataset. And from the R coefficient and linear regression a short discussion was had about how correlated the latitude was to the other meausurement of the plot (i.e. Maximum Temperature, Humidity, Cloudiness, and Wind Speed).

The general conclusion was that maximum temperature was only metric that showed a strong R coeficient of .6 or higher and it showed that our general intuitions are true: the smaller the magnitude of the latitude, the warmer the temperatures.<sup><a name="foot1">1</a></sup>


<sup>[1](#foot1) More specifically the closer one gets to the latitude that is closest to the sun (which for this time of year is about 22&#176;N latitude), the warmer the temperature which varies between 23.5&#176;N and 23.5&#176;S latitude due to the 23.5&#176; tilt of the earth's axis.</sup>

### Part 2
In part 2, the 500+ cities were mapped using hvplots.points onto a global map. Then the list of cities were narrowed down to three criteria:

1. Maximum temperature is between 20&#176;C and 27&#176;C
2. wind speed is less than 4.5 m/s
3. percent cloudiness is zero

This resulted in 9 cities. Then geoapify was used to find a hotel in each city. And, finally, the 9 cities were mapped using hvplots.points.
