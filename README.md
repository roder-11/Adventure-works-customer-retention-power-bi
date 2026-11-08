# Customer Retention & Acquisition Analysis | Power BI

> **Business question:** Adventure Works wins new customers but loses too many after their first purchase. Who are the new customers, how long do they stay, and how many more can we expect to acquire next year?

![Overview dashboard](images/01-overview.png)

## At a glance

| | |
|---|---|
| **Role** | Business Intelligence & Data Analyst |
| **Tool** | Power BI Desktop (DAX, matrix, decomposition tree, forecasting) |
| **Dataset** | Adventure Works sales data (training dataset, no confidential data) |
| **Techniques** | Cohort analysis, retention rate, root-cause drill-down, time-series forecasting |
| **Output** | 6-page interactive report + 2 hidden documentation pages (Synthesis, Conclusion) |
| **Origin** | Final project of the Coursera course *Visualization for Data Analysis with Power BI* |

## Business context

Adventure Works sells outdoor gear in a highly competitive market. Management is worried about the revenue lost when customers do not come back after their first purchase. The report answers three questions:

1. **Cohort behavior:** how do customers acquired in the same month behave over the following 12 months?
2. **First-purchase profile:** which regions, products, genders and customer segments drive new-customer purchases?
3. **Future acquisition:** how many new customers can be expected over the next 12 months, and when are the peaks and dips?

## Key findings

| Question | Finding |
|---|---|
| Best month for new customers in 2022 | **March 2022**, with **933** first-time customers |
| New customers, Dec 2021 to Dec 2022 | **4,931** customers made their first purchase in this rolling year |
| Largest cohort | **December 2021**, with **946** new customers (holiday season) |
| Retention of that cohort | **66%** came back by month 6 (621 of 946), then **60%** in month 7, **54%** in month 8 and **43%** by month 12 |
| Seasonality effect on loyalty | After 3 months, the Dec 2021 cohort retained **39%** versus **24%** for the Jan 2022 cohort: customers won in peak season stay more loyal |
| Strongest first-purchase path | Women buying **Road Bikes** through **retail stores** in **Asia** (retail is about 78% of that segment) |
| Forecast | About **919** first purchases expected in **April 2023** and about **223** in **December 2023** |

## Recommendations

- **Marketing:** focus Road Bikes campaigns on women in Asia, and test whether the same female skew exists in Europe and North America. Male acquisition in Asia looks under-penetrated (18,974 versus 54,127 first-purchase records).
- **Sales channels:** invest in retail partnerships (co-marketing, in-store displays, incentives) while developing online acquisition to diversify the channel mix.
- **Product and inventory:** prioritize Road Bikes stock in Asia, and bundle accessories with bikes (accessories are the weakest category at 25,870 in Asia).
- **Retention:** run post-purchase follow-up in the first 3 months, especially for customers acquired in quiet months, and use the forecast to plan campaigns before expected dips.

## Report pages

| # | Page | What it shows |
|---|---|---|
| 1 | **Overview** | KPI cards (sales, income, quantity, unit price), slicers (product, region, gender, segment), sales by product and region, sales by segment, customers by gender, sales and income trend, sales map |
| 2 | **Cohort Analysis First Purchase** | Matrix of new customers per first-purchase month |
| 3 | **Customer Retention Over Time** | Customers from each cohort who purchased again, from 1 to 12 months after their first purchase |
| 4 | **Customer Retention Rate** | Same matrix as a percentage, with a white-to-green gradient |
| 5 | **Decomposition Tree** | First purchases broken down by region, product, gender and customer segment |
| 6 | **Forecasting First Purchase** | 12-month forecast of new customers (95% confidence interval, seasonality of 10 points) |
| (hidden) | **Synthesis, Conclusion** | Project objectives and written conclusions |

| Cohort retention rate | Decomposition tree | Forecast |
|---|---|---|
| ![Retention rate](images/04-retention-rate.png) | ![Decomposition tree](images/05-decomposition-tree.png) | ![Forecast](images/06-forecast.png) |

## Method

1. **Accessible theme:** *Accessible City Park* for readable contrast.
2. **Data preparation:** typed and formatted fields (date as month and year, currency with 2 decimals, region as geographic category).
3. **Cohort definition:** a calculated column assigns each customer to the month of their first purchase (`First Purchase Date`).
4. **Retention measures:** a `Months After Purchase` table (1 to 12) and two DAX measures, `Customer Retention` and `Customer Retention Rate %`.
5. **Exploration:** decomposition tree on `First Purchase Date` explained by region, gender, product and customer segment.
6. **Forecast:** Power BI forecasting on distinct new customers per month, 12 months ahead.

The DAX is documented in [`dax/measures.md`](dax/measures.md) and the fields in [`docs/data-dictionary.md`](docs/data-dictionary.md).

## Repository structure

```
.
├── README.md
├── powerbi/
│   └── Opportunity_analysis_in_Power_BI.pbix   # open with Power BI Desktop
├── dax/
│   └── measures.md                             # calculated column, table and measures
├── docs/
│   ├── data-dictionary.md
│   └── insights.md                             # detailed answers per report page
└── images/                                     # screenshots used in this README
```

## How to open the report

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free, Windows).
2. Download `powerbi/Opportunity_analysis_in_Power_BI.pbix`.
3. Open it and use the slicers on the Overview page. The report contains its own data, so no refresh is needed.

## What I learned and next steps

- Writing time-intelligence DAX for cohort tracking (`EOMONTH`, `SELECTEDVALUE`, `DISTINCTCOUNT`, `DIVIDE`).
- Turning a chart into a business recommendation, and stating what still needs to be verified.
- **Next step:** rebuild the cohort logic upstream in SQL (PostgreSQL) and orchestrate it, so the dashboard reads a ready-made cohort table. This is part of my move toward data engineering.

## Author

**Rodrigue Awono** | Business Intelligence & Data Analyst, Douala, Cameroon
[LinkedIn](https://www.linkedin.com/in/awonojeanrodrigue-businessintelligence-dataanalyst/)
