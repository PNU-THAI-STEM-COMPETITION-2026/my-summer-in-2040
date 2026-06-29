# Thailand and Korea Daily Weather Data by Location

This repository provides historical daily weather and climate data for the **My City in 2040** student data competition.

The source files contain daily meteorological parameters retrieved from the NASA/POWER (Prediction Of Worldwide Energy Resources) database, representing selected regions in Thailand and South Korea from 1981 through June 28, 2026.

## Files

| File | Latitude | Longitude | Elevation | Description |
|---|---:|---:|---:|---|
| `data/THA/Single_point-Ban-Bueng.csv` | 13.31° N | 101.12° E | 36.27 m | Ban Bueng, Chonburi, Thailand |
| `data/THA/Single_point-Chatuchak:Salaya.csv` | 13.82° N | 100.55° E | 4.48 m | Chatuchak / Salaya, Bangkok/Nakhon Pathom, Thailand |
| `data/THA/Single_point-Chiangmai.csv` | 18.79° N | 98.98° E | 759.08 m | Chiang Mai, Thailand |
| `data/THA/Single_point-Khon-Kaen.csv` | 16.43° N | 102.83° E | 174.92 m | Khon Kaen, Thailand |
| `data/THA/Single_point-Phuket.csv` | 7.88° N | 98.39° E | 10.57 m | Phuket, Thailand |
| `data/KOR/Single_point-Daegu.csv` | 35.87° N | 128.60° E | 241.05 m | Daegu, South Korea |
| `data/KOR/Single_point-Jeju.csv` | 33.50° N | 126.53° E | 53.71 m | Jeju Island, South Korea |
| `data/KOR/Single_point-Pusan.csv` | 35.2309° N | 129.0824° E | 0.98 m | Busan (Pusan), South Korea |
| `data/KOR/Single_point-Seoul.csv` | 37.5546° N | 126.9707° E | 73.25 m | Seoul, South Korea |

Each CSV file contains exactly 16,612 data rows (excluding the header), covering every day from January 1, 1981, to June 25, 2026.

## Column Structure

All CSV files use a consistent nine-column format, containing the column headers directly on the first line.

| Column | Parameter | Description | Unit | Source Model/Sensor |
|---|---|---|---|---|
| `YEAR` | Gregorian Year | Gregorian calendar year (1981–2026) | - | - |
| `DOY` | Day of Year | Sequential day of the year (1–365 or 366 for leap years) | - | - |
| `T2M` | Temperature | Temperature at 2 Meters | °C | MERRA-2 |
| `TS` | Earth Skin Temp | Earth Skin Temperature | °C | MERRA-2 |
| `RH2M` | Relative Humidity | Relative Humidity at 2 Meters | % | MERRA-2 |
| `PRECTOTCORR` | Precipitation | Precipitation Corrected | mm/day | MERRA-2 |
| `WS2M` | Wind Speed | Wind Speed at 2 Meters | m/s | MERRA-2 |
| `WD2M` | Wind Direction | Wind Direction at 2 Meters | Degrees | MERRA-2 |
| `GWETTOP` | Surface Soil Wetness | Surface Soil Wetness | dimensionless (0–1) | MERRA-2 |

## Load the Data in Google Colab

```python
!git clone <REPOSITORY_URL>
%cd <REPOSITORY_DIRECTORY>

import pandas as pd

# Load Thailand Chiang Mai daily weather data
chiangmai = pd.read_csv("data/THA/Single_point-Chiangmai.csv")

# Load South Korea Seoul daily weather data
seoul = pd.read_csv("data/KOR/Single_point-Seoul.csv")

print(seoul.head())
```

## Important Notes

- **Missing Values**: Missing or unavailable source data is represented by `-999.0` or `-999`.
- **MERRA-2 Model Elevation**: The elevations listed in the files represent the average elevation of the 0.5° × 0.625° lat/lon grid cell from the MERRA-2 assimilation model, which may differ slightly from the exact physical elevation of the weather station or city center.

## Sources

NASA Prediction Of Worldwide Energy Resources (POWER) Project:
- [NASA POWER Data Access Viewer](https://power.larc.nasa.gov/data-access-viewer/)
- Data source models: MERRA-2 (Modern-Era Retrospective analysis for Research and Applications, Version 2) and CERES SYN1deg (Clouds and the Earth's Radiant Energy System).

The CSV files use UTF-8 encoding and can be opened with Python, Google Colab, Excel, Tableau, Power BI, or similar tools.
