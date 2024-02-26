```python
import pandas as pd

file_path = "/home/c0d3x/job/forensic/nycflights13/data-raw/airports.csv"
airports_df = pd.read_csv(file_path)

northernmost_airport = airports_df.loc[airports_df['lat'].idxmax()]

print("The northest part is: ")
print(northernmost_airport[['name', 'lat', 'lon']])
```

    The northest part is: 
    name    Dillant Hopkins Airport
    lat                   72.270833
    lon                   42.898333
    Name: 417, dtype: object



```python
import pandas as pd

file_path = "/home/c0d3x/job/forensic/nycflights13/data-raw/airports.csv"
airports_df = pd.read_csv(file_path)

easternmost_airport = airports_df.loc[airports_df['lon'].idxmax()]

print("The eastern part is: ")
print(easternmost_airport[['name', 'lat', 'lon']])
```

    The eastern part is: 
    name    Eareckson As
    lat        52.712275
    lon        174.11362
    Name: 1290, dtype: object



```python
import pandas as pd

weather_file_path = '/home/c0d3x/job/forensic/nycflights13/data-raw/weather.csv'
weather_df = pd.read_csv(weather_file_path)

weather_df['time_hour'] = pd.to_datetime(weather_df['time_hour'])

selected_date = '2013-02-12'
selected_weather = weather_df[weather_df['time_hour'].dt.date == pd.to_datetime(selected_date).date()]

windiest_airport = selected_weather.loc[selected_weather['wind_speed'].idxmax()]['origin']

print("On February 12th, 2013, the New York area airport with the windiest weather was:", windiest_airport)

```

    On February 12th, 2013, the New York area airport with the windiest weather was: EWR



```python

```
