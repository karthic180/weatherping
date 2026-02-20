# 🌦️ Weather ETL Pipeline

A simple yet practical **Data Engineering ETL pipeline** built with Python.
This project extracts current weather data for major European cities using the **Open-Meteo API**, transforms the response, and loads it into a **SQLite** database.

---

##  Overview

This pipeline performs the following steps:

1. **Extract** – Fetches real-time weather data from the Open-Meteo API for:

   * London
   * Paris
   * Berlin
   * Zurich

2. **Transform** – Processes and structures the API response.

3. **Load** – Stores the cleaned data into a SQLite database (`weather.db`).

---

## 🛠️ Tech Stack

* Python 3.x
* SQLite
* Open-Meteo API

---

##  Prerequisites

Make sure you have:

* Python 3.x installed
* `pip` package manager

---

##  Setup Instructions

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/weather-etl-pipeline.git
   cd weather-etl-pipeline
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

---

## ▶️ Running the Pipeline

Run the ETL pipeline with:

```bash
python main.py
```

Once executed, the script will:

* Fetch the latest weather data
* Create (if not exists) a SQLite database file named `weather.db`
* Insert the latest weather records into the `weather` table

---

##  Database Schema

The SQLite database `weather.db` contains a table named `weather` with the following structure:

| Column Name | Type    | Description                           |
| ----------- | ------- | ------------------------------------- |
| id          | INTEGER | Primary Key (Auto-increment)          |
| city        | TEXT    | City name                             |
| temperature | REAL    | Temperature in Celsius                |
| description | TEXT    | Weather description                   |
| humidity    | REAL    | Humidity percentage (nullable)        |
| timestamp   | TEXT    | ISO formatted timestamp of data fetch |

---

## Project Structure

```
weather-etl-pipeline/
│
├── main.py              # Entry point for the ETL pipeline
├── requirements.txt     # Python dependencies
├── weather.db           # SQLite database (generated after running)
└── README.md            # Project documentation
```

---

##  How It Works

* The script sends HTTP requests to the Open-Meteo API.
* The JSON response is parsed and transformed.
* Data is inserted into a SQLite database using Python's built-in `sqlite3` module.

---

##  Future Improvements

* Add logging instead of print statements
* Implement error handling and retries
* Schedule execution with cron or Airflow
* Dockerize the application
* Add historical weather tracking
* Deploy as a cloud-based pipeline

---

##  License

This project is open-source and available under the MIT License.

---
