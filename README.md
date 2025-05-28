

# Castro 311 ETL Pipeline

This Jupyter Notebook powers the ETL workflow behind my personal 311 service request dashboard for San Francisco's Castro neighborhood.

## Features

- 🌐 Fetches current-year 311 data from San Francisco's public Socrata API
- 📍 Converts raw data into a spatial GeoDataFrame using `GeoPandas`
- 🗺️ Projects geometries and buffers requests around a known Castro landmark (Muni stop)
- 🛢️ Outputs processed data to a PostGIS database using SQLAlchemy
- 🌍 Publishes results as a WFS layer via GeoServer

## 🚀 Live Demo

Check out the dashboard built using this ETL pipeline:  
👉 [castro-311-dashboard](https://github.com/danielmyers-xyz/castro-311-dashboard)
- 🔗 WFS Layer (GeoServer): [Castro 311 WFS](https://geoserver.danielmyers.xyz/geoserver/census/castro_311/ows?service=WFS&acceptversions=2.0.0&request=GetCapabilities)

## Requirements

- Python 3.10+
- Required packages (install all with):
  ```
  pip install pandas geopandas shapely requests python-dotenv sqlalchemy psycopg2-binary
  ```

- A `.env` file in the project root with the following:
  ```
  POSTGRES_USER=your_username
  POSTGRES_PASSWORD=your_password
  POSTGRES_HOST=your_host
  POSTGRES_PORT=your_port
  POSTGRES_DB=your_db
  ```

## Usage

1. Clone the repo
2. Add your `.env` file
3. Open `castro_etl.ipynb` in Jupyter Lab or VSCode
4. Run all cells

## Notes

- Data comes from: https://data.sfgov.org/resource/vw6y-z8j6.json
- This ETL pipeline runs automatically once per day on my personal Jupyter Lab server.

---

💡 Maintained by [danielmyers.xyz](https://danielmyers.xyz)
