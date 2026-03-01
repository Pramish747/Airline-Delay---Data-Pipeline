# Airline Delay Data Analysis - Task

##  Project Overview
This project builds a data pipeline and visual analysis on the [Airline Delay Dataset](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay/data) to find patterns and causes behind flight delays across carriers, airports, and months.

---

##  Task 1: Data Pipeline (ETL)

### 1️ Extract
- Loaded raw data from `Airline_Delay_Cause.csv` using pandas

### 2️ Transform
- Checked for duplicate rows — none found
- Dropped rows with missing values (~240 rows out of 171k, so dropping was safe)
- Created two new columns:
  - `total_delay_minutes` = sum of all individual delay causes
  - `on_time_rate` = (arr_flights - arr_del15) / arr_flights

### 3️ Load
- Saved the cleaned dataset as `airline_delay_cleaned.csv`

---

## 📊 Visualizations

###  Correlation Heatmap
Analyzed relationships between carrier delay, weather delay, NAS delay, late aircraft delay, on-time rate, and total arrival delay.

###  Histogram — Distribution of Arrival Delays
Shows the spread of total arrival delay minutes per entry. Result: heavily right-skewed — most rows have low delay but a few are very high.

###  Histogram — Distribution of On-Time Rate
Shows what percentage of flights land on time per route. Most routes sit between 80–85% on time.

###  Bar Plot — Delay Cause Totals
Compared total delay minutes across all 5 causes (carrier, weather, NAS, security, late aircraft) over all years combined.

###  Line Plot — On-Time Rate by Month
Tracked how on-time rates change across months to identify seasonal patterns.

###  Bar Plot — Top 10 Carriers by Average Delay
Shows which carriers have the highest average arrival delay per entry.

---

##  Data Insights

**❓ Which delay cause is the biggest problem?**
Late aircraft delay adds up to the most total delay minutes across all years — not weather. One late plane causes all its next flights to be late too (domino effect). Carrier delays come second.

**❓ Is weather really the biggest cause?**
No. The heatmap and bar chart both show late aircraft and carrier delays have a much bigger impact overall. Weather gets blamed more than it deserves.

**❓ Do delays get worse in certain months?**
Yes. On-time rates clearly drop in June, July, and December — summer thunderstorms and holiday travel are the main drivers. September and October are the most reliable months to fly.

**❓ What is the most common passenger experience?**
Most routes have an on-time rate of 80–85%, meaning roughly 1 in 5 or 6 flights gets delayed. The histogram also shows most entries have low total delay — it's the extreme cases pulling the average up.

---

##  Conclusion
The majority of flights still operate close to schedule. The bigger issue isn't weather — it's late aircraft cascading through the day and carrier-side inefficiencies. Seasonal demand in summer and December noticeably worsens on-time performance across the board.

---

## Libraries Used
- pandas
- numpy
- seaborn
- matplotlib

## How to Run
1. Download the dataset from Kaggle and place `Airline_Delay_Cause.csv` in the same folder
2. Open `airline_delay_pipeline_pramish.ipynb`
3. Run all cells
