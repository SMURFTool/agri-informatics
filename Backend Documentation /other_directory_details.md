# Directory Structure Details

This document provides a detailed description of the key directories used in the SMURF backend project. For API key setup and usage, refer to the main documentation (`SMURF_SETUP.md`).

---

## 1. `api_key/`

This directory contains all the API key files required for external service integrations. These keys are essential for accessing third-party APIs and services used by the SMURF platform.

- **Files typically found here:**
  - `ee-chaitanyamodi-6874ede8f64c.json`: Google Earth Engine service account credentials for satellite data access.
  - `openweather.json`: OpenWeather API key for weather data retrieval.
  - `planet.json`: Planet API key for high-resolution satellite imagery.

**Purpose:**
- Securely store sensitive API credentials outside of the main codebase.
- Enable the backend to authenticate and interact with external APIs.

**Note:**
- API keys have been removed from the repository for security. The variable names and structure are present; kindly generate your own API keys and add them as described. For instructions on obtaining and configuring these keys, see the main documentation (`SMURF_SETUP.md`).

---

## 2. `Images/`

This directory is used to store all satellite and remote sensing imagery downloaded or processed by the backend.

- **Subdirectories:**
  - `sentinel1/`, `sentinel2/`, `landsat/`: Store images from Sentinel-1, Sentinel-2, and Landsat satellites, respectively, retrieved from google earth engine.
  - `planet/`: Stores imagery from the Planet API.

- **Files:**
  - `.tif` files: GeoTIFF images for each village, satellite, and acquisition date.
  - `download_tracking.json`: Tracks the latest image acquisition dates for each village and satellite type.

**Purpose:**
- Centralized storage for all geospatial imagery used in analytics, NDVI calculation, and visualization.
- Supports efficient access and management of large image datasets.

---

## 3. `logs/`

This directory contains all log files generated by backend processes, cron jobs, and data collection scripts.

- **Files typically found here:**
  - `sentinel1_cron.log`, `sentinel2_cron.log`, `landsat_cron.log`: Logs for scheduled satellite data collection jobs.
  - `farm_alerts_cron.log`, `gee_ndvi_health.log`, etc.: Logs for farm alert generation, NDVI health checks, and other backend tasks.
  - `satellite_scheduler.log`: General log for satellite data scheduling and collection.

**Purpose:**
- Record the execution, status, and errors of automated jobs and backend services.
- Facilitate debugging and monitoring of system operations.

---

## 4. `planet_csv/`

This directory is used to store CSV files and tabular data outputs related to Planet satellite imagery and analytics.

- **Files:**
  - CSV files containing metadata derived from Planet imagery.
  - May include exports for further analysis or reporting.

**Purpose:**
- Organize and persist tabular results from satellite data processing.
- Enable easy sharing and downstream use of processed data.

---
