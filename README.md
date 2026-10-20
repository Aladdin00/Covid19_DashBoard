<div align="center">

# 📊 COVID-19 Global Dashboard (Tableau)

**An interactive dashboard tracking global cases, deaths and infection rates, built on data prepared with SQL.**

![Tableau](https://img.shields.io/badge/Tableau-E97627?logo=tableau&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL%20Server-T--SQL-CC2927)
![Excel](https://img.shields.io/badge/Excel-217346?logo=microsoftexcel&logoColor=white)
![Focus](https://img.shields.io/badge/focus-data%20visualization-blue)

[**🔗 View the Live Dashboard on Tableau Public**](https://public.tableau.com/your-link-here)

![Dashboard preview](images/dashboard.png)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Dashboard Components](#dashboard-components)
- [Data Pipeline](#data-pipeline)
- [Tableau Features Used](#tableau-features-used)
- [Key Insights](#key-insights)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Related Project](#related-project)
- [Next Steps](#next-steps)
- [Contact](#contact)

## Overview

This project turns the results of a [COVID-19 SQL data exploration](#related-project) into a single interactive Tableau dashboard. It answers four questions at a glance:

- How many cases and deaths have there been worldwide, and what is the overall death percentage?
- Which continents have been hit hardest in terms of deaths?
- Which countries have the highest share of their population infected?
- How did infection rates change over time in selected countries, and where are they heading?

## Dashboard Components

| # | Visualization | Chart Type | What It Shows |
|---|---------------|------------|---------------|
| 1 | **Global Numbers** | KPI summary | Total cases, total deaths and global death percentage |
| 2 | **Total Deaths per Continent** | Bar chart | Death toll by continent |
| 3 | **Percent Population Infected per Country** | Map | Share of each country's population infected |
| 4 | **Percent Population Infected Over Time** | Line chart with forecast | Infection trend for selected countries with a 95% prediction band |

The time-series view is filtered to six countries for comparison: **United States, United Kingdom, Mexico, India, Egypt and China**.

## Data Pipeline

```
CovidDeaths / CovidVaccinations  →  SQL Server (T-SQL queries)  →  Excel exports  →  Tableau
```

1. **Source data:** COVID-19 deaths and vaccinations tables loaded into SQL Server
2. **Querying:** T-SQL queries calculated total cases, total deaths, death percentage, highest infection count and percent of population infected
3. **Export:** Results from four queries were saved as Excel files (`Tableau table 1–4.xlsx`)
4. **Visualization:** Each Excel file feeds one worksheet, and the four worksheets are combined into a single dashboard

| Excel File | Fields | Used For |
|------------|--------|----------|
| Table 1 | Total cases, total deaths, death percentage | Global numbers |
| Table 2 | Location, total death count | Deaths per continent |
| Table 3 | Location, population, highest infection count, percent population infected | Infection map |
| Table 4 | Location, population, date, highest infection count, percent population infected | Infection trend and forecast |

## Tableau Features Used

- **Multiple data sources:** four separate Excel connections combined in one dashboard
- **Geographic map:** generated latitude and longitude from country names
- **Forecasting:** built-in forecast (automatic seasonality model, 95% prediction bands)
- **Filters:** country filter on the time-series chart
- **Dashboard layout:** worksheets arranged into a single, scrollable view

## Key Insights

> Fill these in with what you see in your final dashboard, for example:

- *The global death percentage sits at about X% across Y million recorded cases*
- *Continent X recorded the highest death toll*
- *Country X had the highest share of its population infected*
- *Infection rates in the selected countries peaked around X*

Specific insights like these make the dashboard much more convincing to recruiters than a generic description.

## Getting Started

### Prerequisites
- [Tableau Desktop](https://www.tableau.com/products/desktop) or the free [Tableau Public](https://public.tableau.com/) app

### Open the dashboard
1. Download `Covid_Dashboard.twb` and the four Excel files (`Tableau table 1–4.xlsx`)
2. Open the workbook in Tableau
3. If prompted, point each data source to the matching Excel file (the workbook was built with local file paths)

> **Tip:** Save the workbook as a packaged workbook (`.twbx`) so the data travels with it and anyone can open it without relinking files.

## Project Structure

```
├── Covid_Dashboard.twb         # Tableau workbook
├── data/
│   ├── Tableau table 1.xlsx    # Global numbers
│   ├── Tableau table 2.xlsx    # Deaths per continent
│   ├── Tableau table 3.xlsx    # Infection rate per country
│   └── Tableau table 4.xlsx    # Infection rate over time
├── images/
│   └── dashboard.png           # Dashboard screenshot
└── README.md
```

## Images 
<img width="1256" height="854" alt="Covid dashboard" src="https://github.com/user-attachments/assets/28554ef2-7a59-4bf6-ade0-bab5f55eab35" />


## Related Project

The data behind this dashboard comes from my **COVID-19 SQL Data Exploration** project, which covers joins, CTEs, temp tables, window functions and views. *(https://github.com/Aladdin00/Covid_19_data_exploration.)*

## Next Steps

- Add vaccination progress using the rolling vaccination view from the SQL project
- Add interactive filters and dashboard actions so selecting a continent updates the other charts
- Create a mobile-friendly dashboard layout

## Contact

Ali Eldin Mohamed · [LinkedIn](https://www.linkedin.com/in/alieldin190)  · alyshaker2004@gmail.com
