#  European Weather ETL Pipeline

A simple and practical ETL (Extract–Transform–Load) pipeline built with Python.  
This project retrieves real‑time weather data for major European cities using the Open‑Meteo API, transforms the data, and loads it into a SQLite database.

---

##  Overview

This pipeline performs the following steps:

### **Extract**
- Uses Open‑Meteo’s Geocoding API to obtain latitude/longitude for each city.
- Fetches current weather data for **40+ major European cities**.

### **Transform**
- Normalizes API responses.
- Extracts temperature, weather code, and timestamp.

### **Load**
- Inserts the cleaned data into a SQLite database (`weather.db`).
- Automatically creates the `weather` table if it does not exist.

---

##  Tech Stack

- **Python 3.x**
- **SQLite**
- **Open‑Meteo Weather API**
- **Open‑Meteo Geocoding API**

---

---

## Installation

Clone the repository:

```bash
git clone https://github.com/your-username/weather-etl.git
cd weather-etl

Install dependencies:

bash
pip install -r requirements.txt


## Running the Pipeline

Run the ETL script:

bash
python main.py
After running:

A SQLite database named weather.db will be created.

A table named weather will be populated with the latest weather data.

Each run inserts a fresh batch of records.

Cities Included
The pipeline currently fetches weather for 40+ major European cities, including:

London

Paris

Berlin

Zurich

Madrid

Rome

Vienna

Prague

Stockholm

Oslo

Helsinki

Lisbon

Amsterdam

Athens

Reykjavik

…and many more

You can easily add or remove cities in the EUROPEAN_CITIES list inside main.py.

How It Works
The script geocodes each city to get latitude/longitude.

It calls the Open‑Meteo weather API for current conditions.

The response is transformed into a clean Python dictionary.

The data is inserted into SQLite using Python’s built‑in sqlite3 module.

How to Use the Menu
Just run:

Code
python menu.py
You’ll see:

Code
=== Weather Menu ===
1. Run ETL (fetch latest weather)
2. View weather for a city
3. Exit
Pick a number and the script handles the rest.
