# Airline Delay - Data Pipeline

Dataset: [Airline Delay Cause - Kaggle](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay/data)

---

## What this project does

A simple ETL pipeline on the airline delay dataset followed by some visualizations to understand what actually causes flight delays.

## Pipeline steps

**Extract** - Loaded the raw CSV using pandas

**Transform** - Cleaned the data:
- Checked for duplicates (found none)
- Found ~240 null values across delay columns, dropped them since they were a small fraction of 171k rows
- Added two new columns:
  - `total_delay_minutes` - sum of all delay causes per row
  - `on_time_rate` - percentage of flights that arrived on time

**Load** - Saved the cleaned data to `airline_delay_cleaned.csv`

## Visualizations

1. **Correlation Heatmap** - shows how delay columns relate to each other
2. **Distribution of Arrival Delays** - right-skewed, most routes have low delay but a few have very high
3. **Distribution of On-Time Rate** - most routes are 80-85% on time
4. **Total Delay Minutes by Cause** - late aircraft is the biggest cause, not weather
5. **Average On-Time Rate by Month** - June, July and December are worst months
6. **Top 10 Carriers by Average Delay** - larger carriers appear higher due to volume, not necessarily poor performance

## Key Insights

- Late aircraft delays cause the most total delay minutes overall, not weather
- On-time rates drop in summer (Jun-Jul) and December — September and October are the safest months to fly
- Most routes are still reliable, with 80-85% on-time rate being the norm
- Security delays are basically zero compared to other causes

## Libraries used

- pandas
- numpy
- seaborn
- matplotlib

## How to run

1. Download the dataset from Kaggle and place `Airline_Delay_Cause.csv` in the same folder
2. Open `airline_delay_pipeline_pramish.ipynb`
3. Run all cells
