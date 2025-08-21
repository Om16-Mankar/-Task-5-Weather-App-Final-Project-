# -Task-5-Weather-App-Final-Project-
# Task 5: Weather App (Final Project)
# Author: Om Keshav Mankar

import requests

# OpenWeather API (free signup at https://openweathermap.org/)
API_KEY = "your_api_key_here"
CITY = "Nagpur"
URL = f"http://api.openweathermap.org/data/2.5/weather?q={CITY}&appid={API_KEY}&units=metric"

# Fetch weather data
response = requests.get(URL)
data = response.json()

if data["cod"] == 200:
    main = data["main"]
    weather = data["weather"][0]
    print(f"🌍 City: {CITY}")
    print(f"🌡️ Temperature: {main['temp']}°C")
    print(f"💧 Humidity: {main['humidity']}%")
    print(f"🌤️ Condition: {weather['description']}")
else:
    print("⚠️ Error fetching data!")
