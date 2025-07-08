# powerbi-covid19-global-analysis
 Global COVID-19 dashboard using Power BI, Python &amp; SQL
# 🦠 COVID-19 Global Data Tracker (Power BI + Python + SQL)

This project is a comprehensive COVID-19 dashboard developed using **Python**, **SQL**, and **Power BI**, with data sourced from [Our World in Data](https://ourworldindata.org/coronavirus). It visualizes global trends in COVID-19 cases, deaths, and vaccinations, offering key insights into the pandemic's spread and containment efforts.

---

## 📌 Key Highlights

- 📊 **Daily and cumulative COVID-19 metrics** – cases, deaths, and vaccinations
- 💉 **Vaccination progress** – % vaccinated population and total doses administered
- 🧮 **Engineered metrics** – Case Fatality Rate (CFR), % Fully Vaccinated
- 📈 **Year-over-Year trends** with time intelligence
- 🌎 **Country and region-level comparisons**

---

## 🛠 Tools & Technologies

- **Python**: Data cleaning, transformation, feature engineering
- **SQL**: Aggregation of daily case and vaccine data by region
- **Power BI**: Dashboard creation and DAX measures
- **DAX Functions**: `SAMEPERIODLASTYEAR`, `CALCULATE`, `DIVIDE`, etc.

---

## 📂 Project Workflow

### 1. Data Collection
- Fetched global COVID-19 data (cases, deaths, vaccines) from [Our World in Data](https://ourworldindata.org/coronavirus)
- Cleaned and structured the data using **Python**
- Added new features like:
  - `% Vaccinated`
  - `Case Fatality Rate = Deaths / Confirmed Cases`

### 2. Data Modeling in SQL
- Wrote SQL queries to:
  - Join case and vaccination tables
  - Aggregate totals by country and region
  - Enable time-series 

```sql
SELECT 
    location,
    date,
    SUM(new_cases) AS total_cases,
    SUM(new_deaths) AS total_deaths,
    SUM(people_fully_vaccinated) AS fully_vaccinated
FROM covid_data
GROUP BY location
3. Power BI Dashboard
Created relationships between country, and metric tables

Built DAX measures:

DAX
Copy
Edit
Total Cases = SUM(COVID[total_cases])
Total Deaths = SUM(COVID[total_deaths])
% Vaccinated = DIVIDE(SUM(COVID[people_fully_vaccinated]), SUM(COVID[population]))
Case Fatality Rate = DIVIDE([Total Deaths], [Total Cases])

📊 Dashboard Features
KPI Cards: Total Cases, Deaths, Vaccination %, and CFR

Clustered Bar/Column Charts: Top countries by vaccinations or deaths

Map Visuals: Global heatmaps of case spread and vaccination rate

Slicers: Country, continent, and date filters (interactive)


