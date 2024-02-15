# python-api-challenge
## *Robertson, J*


### Getting started

* API Keys are required fom GEOAPIFY & OpenWeather and should be saved in an external python or env file & set up next to the VacationPy & WeatherPy Jupyter Notebook files. File should be named api_keys and syntax is:
*  geoapify_key = "api_key"
*  weather_api_key = "api_key"

### Dependencies

* Python version 3.7.13
* hvplot.pandas
* pandas
* requests
* json
* numpy
* matplotlib.pyplot
* scipy.stats
* pathlib
* citipy
 
### Summary of code

Using the openweathermap documentation we can build a current weather request for each location, in this case city, using the following endpoint url.

!['API Request'](code_snippets\url_build_weather_api.png)

The request returns a response which can be passed through the json dependency to be returned in a dictionary format. The individual elements can be called from the json response and saved as variables as below.

The time stored under the 'dt' key is returned in UNIX format. This can be converted into callable list format using the 'time.gmtime' command. By calling the elements of the list in the f' string we can build a human readable date for the output dataframe.

!['API JSON Response'](code_snippets\json_information_slicing.png)

The temperature is returned in Kelvin as is scientific standard. This needs to be converted to celsius using the below code.

!['Temperature conversion'](code_snippets\kelvin_conversion.png)

A scatterplot can be built with the additional properties:
* Title
* X & Y-Axis labels
* Gridlines
* Points formatting

The 'tight_layout' is used to ensure all information is captured in the output .png file.

!['Scatterplot'](code_snippets\scatter_plot_with_properties.png)

The output files are below:
!['Fig1'](output_data\Fig1.png)
!['Fig2'](output_data\Fig2.png)
!['Fig3'](output_data\Fig3.png)
!['Fig4'](output_data\Fig4.png)


To produce regression plots we defined a function requiring two input values to be used for plotting. We can automatically generate regression coefficients, plot line function, position the outputs on the axis and save the image using dynamic naming with the below code. The matplotlib documentation was referred to for the output location for the annotation. The title of the referece columns was tidied up to remove spaces to keep the naming clean.

!['Correlation Regression Function'](code_snippets\defined_function.png)

The output regression plots are as below:

North Latitude vs Cloudiness:

!['North Cloudiness'](output_data\north_Lat_vs_Cloudiness.png)

South Latitude vs Cloudiness:

!['South Cloudiness'](output_data\south_Lat_vs_Cloudiness.png)

North Latitude vs Humidity:

!['North Humidity'](output_data\north_Lat_vs_Humidity.png)

South Latitude vs Humidity:

!['South Humidity'](output_data\south_Lat_vs_Humidity.png)

North Latitude vs Max Temp:

!['North Max Temp'](output_data\north_Lat_vs_MaxTemp.png)

South Latitude vs Max Temp:

!['South Max Temp'](output_data\south_Lat_vs_MaxTemp.png)

North Latitude vs Windspeed:

!['North Windspeed'](output_data\north_Lat_vs_WindSpeed.png)

South Latitude vs Windspeed:

!['South Windspeed'](output_data\south_Lat_vs_WindSpeed.png)


## References 
---

1. openweathermap.org. (2012). Current weather data - OpenWeatherMap. [online] Available at: https://openweathermap.org/current#name [Accessed 11 Feb. 2024].