# CHIME — Climate & Health Impact Modeling

## Research Project | University of Illinois Urbana-Champaign

CHIME (Climate & Health Impact Modeling) is a research project focused on understanding the relationship between environmental conditions and respiratory health outcomes across Illinois counties.

This work is being conducted under the guidance of **Professor Ian Brooks** at the University of Illinois Urbana-Champaign.

The project integrates large-scale healthcare, air-quality, and climate datasets to investigate how environmental conditions such as air quality, temperature, precipitation, and humidity relate to respiratory illness patterns over time.

---

## Research Objectives

The primary objectives of this research are to:

- Analyze respiratory health trends across counties and over time.
- Investigate relationships between air quality and respiratory illnesses.
- Identify seasonal patterns in respiratory disease incidence.
- Explore delayed/lagged relationships between environmental exposure and health outcomes.
- Detect unusual spikes and anomalies in respiratory cases.
- Evaluate predictive models for forecasting respiratory illness trends.
- Develop county-level insights that can support healthcare and public-health preparedness.

---

## Data Sources

The project combines three major data sources:

### 1. Healthcare Data
Healthcare/syndromic surveillance data containing respiratory illness events and associated geographic and temporal information.

### 2. Air Quality Data
Air Quality Index (AQI) data used to investigate relationships between air pollution and respiratory health.

### 3. ERA5 Climate Data
Climate variables obtained from ERA5, including:

- Temperature
- Dew point
- Heat index
- Relative humidity
- Precipitation
- Surface wind
- Surface pressure

---

## Geographic Scope

The analysis focuses on the **Champaign Region of Illinois**, including:

- Champaign
- Clark
- Coles
- Cumberland
- DeWitt
- Douglas
- Edgar
- Ford
- Iroquois
- Livingston
- Piatt
- Macon
- McLean
- Moultrie
- Shelby
- Vermilion

The analysis examines county-level trends across the **2017–2025** period.

---

## Data Engineering Pipeline

The project follows a multi-stage data engineering and research workflow:

```text
Healthcare Data
      │
      ├── Cleaning
      ├── Validation
      ├── Geographic Filtering
      └── Temporal Aggregation
              │
              ▼
       Health Dataset
              │
              │
AQI Data ─────┼───── ERA5 Climate Data
              │
              ▼
      County-Day Integration
              │
              ▼
       Unified Parquet Dataset
              │
              ▼
       Statistical Analysis
              │
              ├── Trend Analysis
              ├── Seasonality
              ├── Lag Effects
              ├── Normality
              └── Anomaly Detection
              │
              ▼
       Predictive Modeling
              │
              ├── Linear Regression
              ├── Random Forest
              ├── Gradient Boosting
              └── XGBoost


REPO STRUCTURE:
CHIME/
│
├── data/
│   └── *.parquet
│
├── notebooks/
│   ├── health_data_cleaning.ipynb
│   ├── climate_data_cleaning.ipynb
│   ├── aqi_data_cleaning.ipynb
│   └── final_analysis.ipynb
│
├── src/
│   └── ...
│
├── README.md
└── requirements.txt
