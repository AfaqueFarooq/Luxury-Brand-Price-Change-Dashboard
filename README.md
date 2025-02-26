# Weekly Price Change & Anomaly Dashboard

## Overview
This project focuses on analyzing weekly price changes for luxury brands by comparing product prices between two consecutive weeks (W and W-1). The goal was to create a dashboard that visualizes price differences, identifies anomalies, and provides actionable insights. The solution processes data from two weekly extracts, calculates price changes, detects outliers, and presents findings in an interactive and user-friendly format.

## Tableau Dashboard
[View Dashboard](https://public.tableau.com/app/profile/afaq.ahmad.farooq/viz/WeeklyPriceChangeAnomalyDashboard/Dashboard?publish=yes)

## Data Preparation and Transformation
### Unpivoting Country-Specific Columns
To make the data more manageable, country-specific price columns were unpivoted into two new columns:
- **Country**: Contains all the country names.
- **Price**: Contains the corresponding price values for each product in the respective country.

### Merge Process
The two datasets (W and W-1) were merged using an outer join based on SKU and Country. This allowed for the current week’s prices and the previous week’s prices to be side by side, enabling the calculation of price differences.

### Dropping Unnecessary Columns
Columns such as Category and URL were dropped to streamline the dataset.

### Calculating Price Differences
- **Price Difference**: Calculated as `(Price in Current Period) – (Price in Previous Period)`.
- **Price Percentage Difference**: Calculated as `((Price in Current Period) – (Price in Previous Period) / (Price in Previous Period)) * 100`.

## Data Visualization
### Price Difference Bar Chart
Visualizes the absolute difference in price for each product, color-coded to indicate positive or negative changes.

### Price Percentage Change Pie Chart
Shows the percentage change in price for each product within a selected brand and country.

### Null Values Bar Chart
Displays the count of null values for both the current and previous weeks across countries.

### KPIs (Key Performance Indicators)
Two KPIs were created to show the total count of null prices for the current and previous weeks.

## Anomalies Identification
- **Null Price Values**: Missing prices for certain products in specific countries were flagged as null values.
- **High Price Differences**: Significant price discrepancies were observed, which need closer scrutiny.

## Next Actions and Recommendations
- **Data Validation**: Investigate and validate missing prices with the tech team.
- **Data Clean-up**: Handle zero price entries or anomalous values carefully.
- **Team Coordination and Feedback Preparation**: Communicate findings back to the Tech and Data teams.
- **Continuous Monitoring**: Set up regular data updates and dashboards to monitor price changes over time.

## Repository Contents
- **Code**: Python scripts for data processing and analysis.
- **Data**: Weekly price extracts used for the analysis.
- **Documentation**: Detailed documentation of the data preparation, transformation, and visualization process.

## Tools Used
- **Python**: For data processing and analysis.
- **Pandas**: For data manipulation.
- **Tableau**: For creating interactive dashboards.

## How to Use
1. Clone the repository.
2. Install the required dependencies.
3. Run the Python scripts to process the data.
4. Open the Tableau dashboard to visualize the results.
