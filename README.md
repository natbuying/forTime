# forTime

## Project Overview
This project analyzes Chicago taxi trip data using GCP's Dataform to build a comprehensive data pipeline and analytics solution.
The project transforms raw taxi trip data into actionable insights about driver performance, operational patterns, and business opportunities.
The findings and visualisations will be build in Looker Studio. (https://lookerstudio.google.com/reporting/65946029-3f42-4b62-98fd-d29990f08eba)

## Technologies Used
- Google Cloud Platform: Cloud infrastructure
- BigQuery: Data warehouse and analytics
- Dataform: Data transformation and pipeline orchestration
- Looker Studio: Data visualization and dashboards
- GitHub Actions: CI/CD automation
- BigQuery SQL: Data transformation language

## Setup Instuctions
Prerequisites
1.Google Cloud Platform account with billing enabled
2.BigQuery API enabled
3.Dataform service enabled
4.Access to bigquery-public-data.chicago_taxi_trips.taxi_trips dataset
5.Looker Studio access (optional, for dashboard viewing)
6.GitHub repository with GitHub Actions enabled

## Installation
1. Clone the repository
```
git clone https://github.com/natbuying/forTime.git
cd timeDevUS
```

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

## Data Pipeline Architecture
1. Staging (staging/) -- Data cleaning and standardization layer
    - stg_taxi_trips: Clean and standardized raw Chicago taxi trip data
    - stg_holidays: US federal holidays reference table
    - stg_driver_shifts: Calculate driver shift patterns and break times

2. Datamart (datamart/) -- Business-specific aggregations / performance metrics layer
    - tip_earners: Top 100 taxi IDs by tip earnings (last 3 months)
    - overworked_drivers: Top 100 overworked drivers analysis
    - holiday_effects: Holiday impact on trip patterns
    - peak_earning_hours: Peak earning hour Insights
    - performing_areas: Performing pickup area insights

3. Analytics (analytics/) -- Dashboard-ready data models
    - driver_workload_metrics: Driver workload analysis with shift patterns
    - trip_metrics: Trip-level calculations (duration, distance, tip rates)
    - holiday_metrics: Trip volume analysis around holidays


##Analytical Questions & Methodology
1.Top 100 taxi IDs by tip earnings in the last 3 months 
Assumptions:
-Analysis period: Last 3 complete months from current date
-Tips include both cash and credit card tips
-Only completed trips with valid tip amounts considered

2. Top 100 Overworked drivers based on shift patterns
Assumptions:
-Minimum 8-hour break required between shifts
-Shift defined as continuous period of activity within 2 hour gaps
-Long shift (overwork) threshold: >12 hours
-Regular overwork: >3 long shifts per week for 4+ weeks
-Analysis covers last 6 months for better identification

3. Holiday Impact Analysis
Assumptions:
-Considering only US Federal holidays
-Impact period: 3 days before and after each holiday
-Baseline: Average of same weekdays in non-holiday periods

4. Additional Insights
Insight 1: Peak earning hours
Business Value:  Enables drivers to optimize their work schedules by identifying high-demand time periods, potentially increasing hourly earnings by targeting peak revenue hours while reducing time spent in low-earning periods.

Insight 2: Performing Areas
Business Value: Helps drivers strategically position themselves in high-value pickup locations, reducing empty miles and wait times while maximizing trip frequency and fare amounts. Fleet operators can use this data for driver deployment and route optimization.

## Looker Studio Dashboard
Dashboard Structure
1.Overview of Chicago Taxi Trips in 2023: Key Overview metrics and trends
2.Performance for the Top 100 Tip Earners in the Q42023: Top earners and workload analysis
3.Top 100 Overworked Drivers in 2H of 2023: Overworkers metrics and distributions
3.Holiday Effectiveness in 2023: Holiday period Impact vs baseline performance
4.Additional Insights: Actionable recommendations - Peak Hours for Drivers and Best performing Pickup Areas


