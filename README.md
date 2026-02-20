# Weather ETL Pipeline

This project is a simple data engineering ETL pipeline that fetches current weather data for major European cities using the Open‑Meteo API and stores the results in a SQLite database.  
A separate query script allows users to view the latest weather for any city stored in the database.

## Prerequisites

- Python 3.x

## Setup

1. Clone or download this repository.
2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

## Running the ETL Pipeline

To fetch the latest weather data for all supported European cities, run:

```
python main.py
```

This will create (or update) a SQLite database named `weather.db` and insert the latest weather records.

## Querying Weather Data

To view the most recent weather for a specific city, run:

```
python weather_query.py
```

You will be shown a list of available cities and prompted to enter the one you want to view.

## Database Schema

The SQLite database `weather.db` contains a table named `weather` with the following columns:

- **id**: Primary key  
- **city**: City name  
- **temperature**: Temperature in Celsius  
- **description**: Weather code from Open‑Meteo  
- **humidity**: Humidity percentage (may be NULL if not available)  
- **timestamp**: ISO‑formatted timestamp of when the data was fetched  

## Project Structure

```
weather-etl/
│
├── main.py              # ETL pipeline (fetch + load)
├── weather_query.py     # User weather lookup tool
├── requirements.txt     # Python dependencies
└── README.md            # Project documentation
```

## Notes

- The ETL pipeline must be run before using the query script.
- You can add or remove cities by editing the `EUROPEAN_CITIES` list in `main.py`.

