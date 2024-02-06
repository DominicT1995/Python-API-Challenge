# Python-API-Challenge
UTSA Data Analytics Bootcamp Python API challenge where the OpenWeatherMap and Geoapify APIs will be used to aggregate, plot, and analyze data for weather trends and vacations.

------------------------------------------------------------------------------------------------------------------
WEATHERPY

Inside the Python-API-Challenge Repository there is an output_data folder used to recieve a weather dataframe from the Weather.ipynb file and the WeatherPy folder. The WeatherPy folder holds the WeatherPy.ipynb and the VacationPy.ipynb files.

------------------------------------------------------------------------------------------------------------------
WeatherPy.ipynb

The WeatherPy.ipynb file utilizes the citipy library to generate a list of the nearest cities to randomly generated latitudes and longitudes. The OpenWeatherMap API is then used to fetch current weather data for each of the listed cities. Weather data parsed for includes: city name, latitude, longitude, max temperature, humidity, cloudiness, wind speed, country, and date. The pandas library is then utilized to convert the parsed data into a dataframe that is outputted as the cities.csv file to the output_data folder for ease of access and to remove need of further API calls to acquire data.

The WeatherPy.ibynb file will then take the dataframe created and create various scatterplots comparing city latitude to max temperature, humidity, cloudiness, and wind speed. The dataframe will then be split according to city latitudes above 0 and below 0 to represent cities in the northern and southern hemispheres. Scatterplots and linear regressions will then be performed on each hemisphere for city latitude against max temperature, humidity, cloudiness, and wind speed with correlation analysis for each variable.

------------------------------------------------------------------------------------------------------------------
VacationPy.ipynb

The VacationPy.ipynb file will load in the cities.csv file as a pandas dataframe from the output_data folder. The hvplot dependency will be used to create a world map of all cities with size based on humidity percentage for vizualization. The dataframe will then be narrowed according to weather preferences and copied to a new dataframe that will recieve the nearest hotel within 10,000 meters for each city from the Geoapify API. The file will then plot a new world map with all cities meeting weather preferences with listed nearest hotel and country.