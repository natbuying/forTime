# forTime


## Project Structure

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

