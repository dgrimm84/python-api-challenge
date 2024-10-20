# python-api-challenge
# Part 1 | WeatherPy
## Description of files for this part of the challenge
> - the WeatherPy.py file generates a list of random latitude and longitude values, uses these values in the Citypy library in order to locate the nearest cities to these random coordinates.  Then, it calls the OpenWeather API, passes in the city names that are generated, and then creates a dataframe that stores City Name, Latitude, Longitude, Max Temp, Humidity, Clouds, Wind Speed, Country, and date.  This dataframe is then outputted into a CSV file.  With this dataframe, scatter plots are created for the relationships between Latitude & Temp, Latitude & Humidity, Latitude and Clouds, and Latitude and Wind Speed.  With these scatter plots, regression calculations and plots are created to represent the relationship of these values in the North and South Hemispheres.  

### Discussion about the linear relationship of Latitude vs. Temperature

![Alt text](/WeatherPy/output_data/Fig5.png)

> ### Northern Hemisphere
> - There is a negative correlation (indicated with a slope of -0.87) meaning that as the latitude decreases (moving closer to the North pole) the temperature decreases
> - The equation of y=−0.87x+92.39 indicates that with each decrease in latitude by 1 degree, the temperature goes down by 0.87 degrees.  And, 92.39 indcates the estimated temperature at 0 latitude (the equator) based on these trends.
> - The r-value of -0.80 signifies that the negative correlation is significant but not perfect.  This means that while a higher latitude does have a strong correlation to decreasing temperature, there are enough outliers to signify that there is still an influence of other factors in this relationship

![Alt text](/WeatherPy/output_data/Fig6.png)

> ### Southern Hemisphere
> - There is a positive correlation (indicated with a slope of 0.14) meaning that as the latitude increases (moving closer to the equator) the temperature increases
> - The equation of y=−0.57x+87.32 indicates that with each increase in latitude by 1 degree, the temperature goes up by 0.57 degrees.  And, 82.32 indcates the estimated temperature at 0 latitude (the equator) based on these trends.
> - The r-value of -0.68 signifies that the positive correlation is relatively weak.   This means that the positive correlation between temperature and latitude in the Southern Hemisphere is weaker than the Northern Hemisphere and other factors play a larger role in this comparison



# Discussion about the linear relationship of Latitude vs. Humidity

![Alt text](/WeatherPy/output_data/Fig7.png)

> ### Northern Hemisphere
> - There is a positive correlation (indicated with a slope of 0.15) meaning that as the latitude increases (moving closer to the North pole) the humidity increases ever so slightly
> - The equation of y=−0.15x+64.26 indicates that with each decrease in latitude by 1 degree, the humidity goes up by 0.12 percent.  And, 64.26 indcates the estimated humidity percentage at 0 latitude (the equator) based on these trends.
> - The r-value of 0.12 signifies that the positive correlation is almost non-existant.  This means that increasing latitude hardly affects the humidity percentage at all.  

![Alt text](/WeatherPy/output_data/Fig8.png)

> ### Southern Hemisphere
> - There is a positive correlation (indicated with a slope of 0.12) meaning that as the latitude increases (moving closer to the equator) the humidity increases
> - The equation of y=0.12x+72.2 indicates that with each increase in latitude by 1 degree, the humidity goes up by 0.12 percent.  And, 72.2 indcates the estimated humidity percentage at 0 latitude (the equator) based on these trends.
> - The r-value of 0.07 signifies that the positive correlation is extremely weak.   This means that the positive correlation between temperature and latitude in the Southern Hemisphere is even weaker than the already-weak Northern Hemisphere and other factors play an almost total role in this relationship


# Discussion about the linear relationship of Latitude vs. Cloudiness

![Alt text](/WeatherPy/output_data/Fig9.png)

> ### Northern Hemisphere
> - There is an extremely weak positive correlation (indicated with a slope of 0.09) meaning that as the latitude increases (moving closer to the North pole) the cloudiness increases at a very small rate
> - The equation of y = 0.09x + 57.19 indicates that with each decrease in latitude by 1 degree, the cloudiness goes up by 0.09 percent.  And, 54.19 indcates the estimated cloudiness percentage at 0 latitude (the equator) based on these trends.
> - The r-value of 0..09 signifies that the positive correlation is almost non-existant.  This means that increasing latitude hardly affects the cloudiness percentage at all.  

![Alt text](/WeatherPy/output_data/Fig10.png)

> ### Southern Hemisphere
> - There is a positive correlation (indicated with a slope of 0.09) meaning that as the latitude increases (moving closer to the equator) the cloudiness increases at a very small rate
> - The equation of y = 0.09x + 54.19 indicates that with each increase in latitude by 1 degree, the cloudiness goes up by 0.09 percent.  And, 54.19 indcates the estimated humidity percentage at 0 latitude (the equator) based on these trends.
> - The r-value of 0.03 signifies that the positive correlation is almost non-exsitant.   This means that the positive correlation between cloudiness and latitude in the Southern Hemisphere is even weaker than the already-weak Northern Hemisphere and other factors play an almost total role in this relationship


# Discussion about the linear relationship of Latitude vs. Wind Speed

![Alt text](/WeatherPy/output_data/Fig11.png)

> ### Northern Hemisphere
> - There is an extremely weak positive correlation (indicated with a slope of 0.09) meaning that as the latitude increases (moving closer to the North pole) the wind speed increases at a very small rate
> - The equation of y = 0.03x + 7.39 indicates that with each decrease in latitude by 1 degree, the wind speed goes up by 0.03 miles per hour.  And, 7.39 indcates the estimated wind speed at 0 latitude (the equator) based on these trends.
> - The r-value of 0.09 signifies that the positive correlation is almost non-existant.  This means that increasing latitude hardly affects the wind speed at all.  

![Alt text](/WeatherPy/output_data/Fig12.png)

> ### Southern Hemisphere
> - There is a negative correlation (indicated with a slope of -0.11) meaning that as the latitude increases (moving closer to the equator) the wind speed decreases at a small rate
> - The equation of y = -0.11x + 6.94 indicates that with each increase in latitude by 1 degree, the wind speed goes down -0.11 miles per hour.  And, 6.94 indcates the estimated wind speed at 0 latitude (the equator) based on these trends.
> - The r-value of-0.28 signifies that the negative correlation is small but present.   This means that the negative correlation between wind speed and latitude in the Southern Hemisphere is slightly stronger than the Northern Hemisphere but other factors still play a very large total role in this relationship

# Part 2 | VacationPy
## Description of files for this part of the challenge

> - The VacationPy.ipynb file calls the previously created cities.csv file, creates a dataframe from this information, filters this dataframe into locations that are between 80 and 90 degrees Farhenheit, cloudiness less than 2, and wind speed less than 20 mph to display just the preferred vacation locations based on weather.  Then, this filtered dataframe is plotted into an interactive world map with dots located at each resulting city.  The size of the dot is the value of the humidity.  

![Alt text](/WeatherPy/output_data/first_map_sample.png)

> - Then, this dataframe is passed into the geoapify library with a radius of 10,000 meters around each latitude and longitude result.  These results are then used to find the nearest hotels to each city location.  A "Hotel Name" Column is added and the results for each of these searched are stored in the dataframe
> - Finally, this hotel_df is passed through a final check to remove the "No Hotel was Found!" rows since we don't want to display the cities with no hotels within 10,000 meters.  Then, this final filtered hotel_df is plotted into an interactive world map with the same parameters as above, but now the user can hover over any point to display Latitude, Longitude, City, Humidity, Hotel, and Country.

![Alt text](/WeatherPy/output_data/final_hotal_map_sample.png)
