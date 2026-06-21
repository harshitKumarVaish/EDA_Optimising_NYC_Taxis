# Optimising NYC Taxi Operations with EDA

Exploratory data analysis project on 2023 New York City Yellow Taxi trip records. The objective was to identify demand patterns, revenue drivers, route inefficiencies, and pricing opportunities that could help a taxi operator improve dispatching, fleet allocation, and customer experience.

## Project Overview

This analysis uses NYC Taxi and Limousine Commission Yellow Taxi trip data for 2023. The dataset includes pickup and drop-off timestamps, passenger counts, trip distances, pickup and drop-off zones, payment types, fares, tips, tolls, surcharges, and total trip amounts.

The project covers:

- Loading and combining monthly parquet trip records
- Cleaning missing values, invalid categories, duplicate fee columns, and outliers
- Temporal analysis of hourly, daily, monthly, and quarterly demand
- Financial analysis of fare amount, tip amount, total revenue, and surcharges
- Geographic analysis of pickup and drop-off zones using NYC taxi zone shapefiles
- Route and speed analysis to identify operational bottlenecks
- Pricing recommendations based on demand, distance tiers, vendor behavior, and time of day

## Dataset

- Source: NYC Taxi and Limousine Commission Yellow Taxi trip records
- Period analysed: 2023
- Initial records loaded: 3,041,714
- Key fields: pickup/drop-off datetime, passenger count, trip distance, pickup/drop-off zone, payment type, fare amount, tip amount, total amount, congestion surcharge, airport fee

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- GeoPandas
- Jupyter Notebook

Recommended library versions used in the notebook:

- NumPy 1.26.4
- Pandas 2.2.2
- Matplotlib 3.10.0
- Seaborn 0.13.2

## Analysis Workflow

1. Data Loading
   - Loaded monthly 2023 Yellow Taxi parquet files.
   - Reviewed schema, row counts, data types, and summary statistics.

2. Data Cleaning
   - Combined duplicate airport fee columns.
   - Imputed missing passenger count, rate code, congestion surcharge, and airport fee values.
   - Removed invalid passenger counts, payment types, unrealistic fares, and extreme trip-distance outliers.
   - Created derived fields such as pickup hour, day of week, month, quarter, trip duration, route, distance tier, fare per mile, and tip percentage.

3. Exploratory Data Analysis
   - Analysed pickup demand by hour, weekday/weekend, month, and quarter.
   - Compared monthly and quarterly revenue trends.
   - Studied relationships between trip distance, fare amount, trip duration, passenger count, and tip amount.
   - Mapped pickup and drop-off demand across taxi zones.
   - Identified high-demand zones and slow routes by hour.

4. Strategy Recommendations
   - Suggested fleet deployment changes for peak hours and high-demand zones.
   - Proposed SUV allocation in zones with higher average passenger counts.
   - Recommended dynamic pricing during high-demand periods and discounts during quieter hours.
   - Proposed distance-tier pricing, with premium pricing for short trips and competitive pricing for longer trips.

## Key Findings

- Taxi demand is highest during daytime and evening peak hours, especially from 9 AM to 6 PM.
- Daytime revenue is much larger than nighttime revenue, with approximately USD 5.83M during daytime hours versus USD 0.81M during nighttime hours in the analysed data.
- Trip distance and fare amount have a strong positive correlation of about 0.95.
- Tip amount also shows a strong relationship with trip distance, with a correlation of about 0.79.
- Passenger count has very low correlation with fare amount, indicating fares are driven mainly by distance, duration, and surcharges rather than number of riders.
- Top pickup zones include Upper East Side South, Midtown Center, Upper East Side North, JFK Airport, Midtown East, LaGuardia Airport, Lincoln Square East, Penn Station/Madison Sq West, Times Sq/Theatre District, and Murray Hill.
- Top drop-off zones include Upper East Side North, Upper East Side South, Midtown Center, Murray Hill, Upper West Side South, Lincoln Square East, Midtown East, Lenox Hill West, Times Sq/Theatre District, and East Chelsea.
- Airport and Manhattan business/leisure zones show strong demand concentration and should be prioritised for dispatch planning.
- Short trips have higher average fare per mile than longer trips, supporting a tiered pricing strategy.

## Business Recommendations

- Increase cab availability in high-demand zones such as Upper East Side South, Midtown Center, JFK Airport, LaGuardia Airport, Times Sq/Theatre District, and Penn Station/Madison Sq West.
- Deploy more vehicles between 9 AM and 6 PM to match peak pickup demand.
- Maintain targeted nighttime availability in nightlife and airport-heavy zones such as East Village, West Village, JFK Airport, Lower East Side, and Times Sq/Theatre District.
- Use dynamic pricing during peak demand windows and offer lower fares or promotions during quieter late-night hours.
- Apply tier-based pricing by trip distance: premium rates for short trips, stable rates for medium trips, and competitive rates for long trips.
- Place larger vehicles in zones with higher average passenger counts to improve passenger experience and vehicle utilization.

## Repository Files

- `Harshit_Kumar_Vaish_EDA_Optimising_NYC_Taxis.ipynb` - Jupyter notebook containing the full EDA workflow, visualisations, and recommendations.
- `Harshit_Kumar_Vaish_EDA_Optimising_NYC_Taxis_report.pdf` - Project report summarising the analysis.

