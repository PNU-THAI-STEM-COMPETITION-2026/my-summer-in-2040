# NASA/POWER Daily Climate and Weather Data

## Processed competition dataset

### Dataset summary for competition administrators

Row counts below exclude the NASA metadata header (18 lines) and the CSV header line.

| File | Location | Target years | Data rows | Columns |
|---|---|---:|---:|---|
| `THA/Single_point-Ban-Bueng.csv` | 13.31° N, 101.12° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `THA/Single_point-Chatuchak:Salaya.csv` | 13.82° N, 100.55° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `THA/Single_point-Chiangmai.csv` | 18.79° N, 98.98° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `THA/Single_point-Khon-Kaen.csv` | 16.43° N, 102.83° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `THA/Single_point-Phuket.csv` | 7.88° N, 98.39° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `KOR/Single_point-Daegu.csv` | 35.87° N, 128.60° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `KOR/Single_point-Jeju.csv` | 33.50° N, 126.53° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `KOR/Single_point-Pusan.csv` | 35.2309° N, 129.0824° E | 1981 through June 2026 (46 years) | 16,615 | 12 |
| `KOR/Single_point-Seoul.csv` | 37.5546° N, 126.9707° E | 1981 through June 2026 (46 years) | 16,615 | 12 |

All files use the same twelve-column format:

| Column | Parameter | Description |
|---|---|---|
| `YEAR` | Gregorian Year | Gregorian calendar year (1981–2026) |
| `DOY` | Day of Year | Sequential day of the year (1–365 or 366 for leap years) |
| `ALLSKY_SFC_SW_DWN` | Solar Irradiance | All Sky Surface Shortwave Downward Irradiance (MJ/m²/day) |
| `ALLSKY_SFC_UV_INDEX` | UV Index | All Sky Surface UV Index (dimensionless, W/m² × 40) |
| `T2M` | Temperature | Temperature at 2 Meters (°C) |
| `TS` | Earth Skin Temp | Earth Skin Temperature (°C) |
| `RH2M` | Relative Humidity | Relative Humidity at 2 Meters (%) |
| `PRECTOTCORR` | Precipitation | Precipitation Corrected (mm/day) |
| `PS` | Surface Pressure | Surface Pressure (kPa) |
| `WS2M` | Wind Speed | Wind Speed at 2 Meters (m/s) |
| `WD2M` | Wind Direction | Wind Direction at 2 Meters (Degrees) |
| `GWETTOP` | Surface Soil Wetness | Surface Soil Wetness (dimensionless, 0–1) |

## Data limitations and missing values

- **CERES Solar & UV Index**: Solar irradiance (`ALLSKY_SFC_SW_DWN`) and UV Index (`ALLSKY_SFC_UV_INDEX`) are satellite-derived measurements from the CERES SYN1deg project. Because these sensors were launched later, data prior to March 2000 is unavailable and marked as `-999.0`.
- **Precipitation model limitations**: Corrected precipitation (`PRECTOTCORR`) is model-simulated from MERRA-2, which provides high temporal resolution but can sometimes over- or under-estimate localized convective storms compared to ground station gauges.
- **LST (Local Solar Time)**: The daily values are aggregated based on Local Solar Time (LST) to align with natural diurnal cycles.

## Source and intermediate files

- **Source agency**: NASA Langley Research Center POWER Project
- **API and Portal**: [NASA POWER API Portal](https://power.larc.nasa.gov/)
- **Data Source Models**:
  - MERRA-2 (Modern-Era Retrospective analysis for Research and Applications, Version 2)
  - CERES SYN1deg (Clouds and the Earth's Radiant Energy System, 1-degree resolution)
