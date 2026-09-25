# 🌦️ Weather API Explorer

A Python project that explores REST API consumption, JSON parsing, and data analysis by building an increasingly capable weather tool — from a single interactive lookup to a multi-city comparison engine to a past/present/forecast analytics tool.

Built as hands-on practice following the IBM Python for Data Science course, with a focus on real API integration rather than static datasets.

---

## 📌 Overview

This project uses the [Open-Meteo API](https://open-meteo.com/) (free, no API key required) to:
- Convert a city name into coordinates via the **Geocoding API**
- Fetch live and forecasted weather data via the **Forecast API**
- Process, compare, and summarize that data using Python, classes, and NumPy

The project evolved in three stages, each adding a new layer of complexity and a new core skill.

---

## 🚀 Version 1 — Single-City Weather Lookup

**What it does:**
Takes a city name as input, geocodes it to latitude/longitude, fetches current weather, and prints a clean, human-readable summary (temperature and windspeed).

**Core skills practiced:**
- Making GET requests with the `requests` library
- Parsing nested JSON responses
- Chaining two APIs together (geocoding → weather)
- String formatting for readable output

---

## 🏙️ Version 2 — Multi-City Comparison

**What it does:**
Accepts a comma-separated list of cities, fetches the current temperature for each, and identifies which city is the hottest.

**Core skills practiced:**
- Object-oriented programming — a `Temp` class that handles the full geocode → fetch → store pipeline internally on initialization
- Building and storing a list of objects (not just raw values)
- Using `max()` with a `key=lambda` argument to compare objects by a specific attribute
- Real-world API limitations (e.g., handling inputs the geocoding API doesn't recognize, like state/region names instead of cities)

---

## 📊 Version 3 — Past / Present / Forecast Analysis

**What it does:**
For a single city, fetches:
- The **current** temperature (live reading)
- The **average temperature over the past 3 days**
- The **average forecasted temperature for the next 2 days**

and prints all three as a readable summary.

**Core skills practiced:**
- Using Open-Meteo's `past_days` and `forecast_days` parameters to pull a multi-day window in a single API call
- Working with parallel lists (`time[]` and `temperature_2m_max[]`) and slicing around a specific index
- Writing a reusable function to calculate an average (via `numpy.mean()`)
- Returning and unpacking multiple values from a function
- f-strings for dynamic, readable output

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python | Core language |
| `requests` | HTTP requests to the APIs |
| `numpy` | Averaging temperature data |
| Jupyter Notebook | Development environment |
| [Open-Meteo Geocoding API](https://open-meteo.com/en/docs/geocoding-api) | City name → coordinates |
| [Open-Meteo Forecast API](https://open-meteo.com/en/docs/) | Current, historical, and forecast weather data |

---

## ▶️ How to Run

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install requests numpy
   ```
3. Open `weather_api.ipynb` in Jupyter Notebook or VS Code
4. Run the cells for whichever version you'd like to try, and enter a city name when prompted

---

## 📂 Project Structure

```
weather-api-project/
│
├── weather_api.ipynb   # Contains all three versions
└── README.md
```

---

## 🎯 What I Learned

- How to chain multiple APIs together to build a single working pipeline
- Why classes become useful once you're managing multiple related objects, not just one value
- The difference between comparing raw objects vs. comparing them by a specific attribute (`key=`)
- How to slice and index parallel lists to separate meaningful groups of data (past vs. future)
- Why functions matter once the same logic (like averaging) needs to run more than once

---

## 🔭 What's Next

- **Streamlit front end** — turning this into a clickable, shareable web app instead of a notebook-only tool
- Possibly extending to a 7-day forecast view with a line chart, similar to the trend chart built in my [sales data analysis project](#)

---

## 👤 Author

Armeen Kaur — BCA student, building a project-based path toward data analytics and machine learning.
