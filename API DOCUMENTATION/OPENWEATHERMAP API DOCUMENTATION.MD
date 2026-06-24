# **openweathermap API Documentation**

getting current weather data and forecast data using openweathermap API

### overview

you can access current weather data or forecast data of any location. it includes

- current weather data
    
- 5 days/3 hours forecast data
    

weather data is available in JSON or XML or HTML

_**This API is useful for both Beginners and Developers**_

Beginners - who wants to work with REST API

Developers - Who are familiar with using REST API to integrate weather data in thier web or mobile applications.

**How to get API key**

- go to openweathermap API website
    
- login to the website
    
- go to API Keys section
    
- get your API keys
    

#### KEY CONCEPTS

1. WEATHER DATA **VS** FORECAST DATA
    

the `/weather` data gives current weather data for a location. while `/forecast` data gives future prediction at 3 hour intervals .

2\. UNIT SYSTEM

In response temperature is returned in kelvin by default unless unit is specified. temperature can be returned with units like metric, imperial.

3\. INPUT METHODS

weather can be fetched using city name, zip code or coordinates.

4\. API KEY

Every request requires API key `appid` for secure data tranfer which must kept safe.

#### How to call API for current weather data

API CALL

you can fetch current weather data using city name or zip code also.

[<code>https://api.openweathermap.org/data/2.5/weather?lat={lat}&amp;lon={lon}&amp;appid={API</code>](https://api.openweathermap.org/data/2.5/weather?lat=%7Blat%7D&lon=%7Blon%7D&appid=%7BAPI) `key}`

**parameters**

| **Parameter name** | **Type** | **Required** | **Description** |
| --- | --- | --- | --- |
| lan | integer | yes | Latitude. If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around. |
| lat | Integer | yes | Latitude. If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around |
| city name | string | yes | Access weather data directly using city name or country code. |
| units | string | optional | units fo rmeasurement metrics and imperial are available. if you don't use unit mode kelvin will used by default. |
| mode | string | optional | Response format available in XML or HTML. if you don't use it, response format will be JSON by default |

Examle of API call

[<code>https://api.openweathermap.org/data/2.5/weather?lon=77.6033&amp;lat=12.9762&amp;appid={{apikey}}</code>](https://api.openweathermap.org/data/2.5/weather?lon=77.6033&lat=12.9762&appid=%7B%7Bapikey%7D%7D)

**API Response**

JSON

```
{
    "coord": {
        "lon": 77.6033,
        "lat": 12.9762
    },
    "weather": [
        {
            "main": "Clouds",
            "description": "scattered clouds",
         }
    ],
    "base": "stations",
    "main": {
        "temp": 305.74,
        "humidity": 38,
    },
      "wind": {
        "speed": 8.94,
    },
    "clouds": {
        "all": 40
    },
    "dt": 1777895534
    "timezone": 19800,
    "id": 1277333,
    "name": "Bengaluru",
    "cod": 200
}

 ```

##### JSON Format API Response field

- coord.lon - longitude of the location
- coord.lat - latitude of the location
- weather.main - group of weather parameter
- weather.description - condition of the weather
- base - internal parameters
- main
- main.temp - temperature (units : standard by default use others like metric or imperial)
- main.humidity - humidity
- wind
- wind.speed - speed of the wind
- clouds
- clouds.all - cloudiness
- dt - time of data calculation
- timezone - Shift in seconds from UTC
- id - City ID.
- name - City name.
- cod - Internal parameter
    

#### How to call API for 5 days forecast data

API CALL

you can fetch 5 days forecast weather data using city name or zip code also.

[https://api.openweathermap.org/data/2.5/forecast?lat=16.5&amp;lon=75.05&amp;cnt=5&amp;appid={{apikey}}](https://api.openweathermap.org/data/2.5/forecast?lat=16.5&lon=75.05&cnt=5&appid=%7B%7Bapikey%7D%7D)

**parameters**

| **Parameter name** | **Type** | **Required** | **Description** |
| --- | --- | --- | --- |
| lan | integer | yes | Latitude. If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around. |
| lat | Integer | yes | Latitude. If you need the geocoder to automatic convert city names and zip-codes to geo coordinates and the other way around |
| city name | string | yes | Access weather data directly using city name or country code. |
| units | string | optional | units fo rmeasurement metrics and imperial are available. if you don't use unit mode kelvin will used by default. |
| mode | string | optional | Response format available in XML or HTML. if you don't use it, response format will be JSON by default |
| cnt | number | optional | numer of timestamps in response |

Examle of API call

[https://api.openweathermap.org/data/2.5/forecast?lat=16.5&amp;lon=75.05&amp;cnt=5&amp;appid={{apikey}}](https://api.openweathermap.org/data/2.5/forecast?lat=16.5&lon=75.05&cnt=5&appid=%7B%7Bapikey%7D%7D)

API RESPONSE

JSON

```
{
    "cod": "200",
    "message": 0,
    "cnt": 2,
    "list": [
        {
            "dt": 1780995600,
            "main": {
                "temp": 300.27,
                "feels_like": 302.03,
                "temp_min": 300.27,
                "temp_max": 301.1,
                "pressure": 1009,
                "sea_level": 1009,
                "grnd_level": 945,
                "humidity": 68,
                "temp_kf": -0.83
            },
            "weather": [
                {
                    "id": 804,
                    "main": "Clouds",
                    "description": "overcast clouds",
                    "icon": "04d"
                }
            ],
            "clouds": {
                "all": 97
            },
            "wind": {
                "speed": 5.46,
                "deg": 263,
                "gust": 5.74
            },
            "visibility": 10000,
            "pop": 0,
            "sys": {
                "pod": "d"
            },
            "dt_txt": "2026-06-09 09:00:00"
        },
        {
            "dt": 1781006400,
            "main": {
                "temp": 300.02,
                "feels_like": 301.64,
                "temp_min": 300.02,
                "temp_max": 300.11,
                "pressure": 1008,
                "sea_level": 1008,
                "grnd_level": 945,
                "humidity": 68,
                "temp_kf": -0.09
            },
            "weather": [
                {
                    "id": 804,
                    "main": "Clouds",
                    "description": "overcast clouds",
                    "icon": "04d"
                }
            ],
            "clouds": {
                "all": 96
            },
            "wind": {
                "speed": 4.62,
                "deg": 281,
                "gust": 6.61
            },
            "visibility": 10000,
            "pop": 0,
            "sys": {
                "pod": "d"
            },
            "dt_txt": "2026-06-09 12:00:00"
        }
    ],
    "city": {
        "id": 1254727,
        "name": "Terdāl",
        "coord": {
            "lat": 16.5,
            "lon": 75.05
        },
        "country": "IN",
        "population": 26411,
        "timezone": 19800,
        "sunrise": 1780964792,
        "sunset": 1781011899
    }
}

 ```

##### JSON Format API Response field

- `cod` - internal parameter
    
- `cnt` - number of timestamps from response
    
- `list.dt` - Time of data forecasted, Unix
    
- `list.main.temp` - Temperature.
    
- `list.main.feels_like` - This temperature parameter is for the human feeling of weather.
    
- `list.main.temp_min` - Minimum forecast temperature at the moment of calculation. Unit Default: Kelvin, Metric: Celsius, Imperial: Fahrenheit
    
- `list.main.temp_max` - Maximum forecast temperature at the moment of calculation.
    
- `list.main.pressure` - pressure on the sea level by default
    
- `list.main.sea_level` - Atmospheric pressure on the sea level
    
- `list.main.grnd_level` - Atmospheric pressure on the ground level
    
- `list.main.humidity` - Humidity, %
    
- `list.main.temp_kf` - Internal parameter
    
- `list.weatherlist.weather.id` - Weather condition id
    
- `list.weather.main` - Group of weather parameters (Rain, Snow, Clouds etc.)
    
- `list.weather.description` - Weather condition within the group.
    
- `list.weather.icon` - Weather icon id
    
- `list.cloudslist.clouds.all` - Cloudiness, %
    
- `list.windlist.wind.speed` - Wind speed.
    
- `list.wind.deg` - Wind direction.
    
- `list.wind.gust` - Wind gust.
    
- `list.rainlist.rain.1h` - Rain volume .
    
- `list.snowlist.snow.1h` - Snow volume.
    
- `list.visibility` - Average visibility.
    
- `list.pop` - Probability of precipitation.
    
- `list.syslist.sys.pod` - Part of the day (n - night, d - day).
    
- `list.dt_txt` - Time of data forecasted.
    
- `citycity.id` - City ID.
    
- `city.name` - City name.
    
- `city.coordcity.coord.lat` - Geo location, latitude.
    
- `city.coord.lon` - Geo location, longitude.
    
- `country` - Country code.
    
- `timezone` - Shift in seconds.
    
- `sunrise` - Sunrise time.
    
- `sunset` - Sunset time.
    

#### common mistakes (different state codes)

- Invalid API Key - 401 unauthorized error
    
- missing values in request - 400 Bad request
    
- wrong endpoint or parameter - 404 not found




