# forTime

## Project Overview
This project analyzes Chicago taxi trip data using GCP's Dataform to build a comprehensive data pipeline and analytics solution.
The project transforms raw taxi trip data into actionable insights about driver performance, operational patterns, and business opportunities.
The findings and visualisations will be build in Looker Studio.

## Setup Instuctions
Prerequisites
1.Google Cloud Platform account with billing enabled
2.BigQuery API enabled
3.Dataform service enabled
4.Access to bigquery-public-data.chicago_taxi_trips.taxi_trips dataset

## Project Structure

```
timeDevUS/
├── README.md
├── workflow_settings.yaml
├── .gitignore
├── .github/
│   └── workflows/
│      └── dataform.yaml
├── definitions/
│   ├── sources/
│   │   ├── chicago_taxi_trips.sqlx
│   ├── staging/
│   │   ├── stg_taxi_trips.sqlx
│   │   ├── stg_holidays.sqlx
│   │   └── stg_driver_shifts.sqlx
│   ├── datamart/
│   │   ├── tip_earners.sqlx
│   │   ├── overworked_drivers.sqlx
│   │   ├── holiday_effects.sqlx
│   │   ├── peak_earning_hours.sqlx
│   │   ├── performing_areas.sqlx
│   │   └── insights.sqlx
│   └── analytics/
│       ├── driver_workload_metrics.sqlx
│       ├── holiday_metrics.sqlx
│       └── trip_metrics.sqlx
└── includes/
```

