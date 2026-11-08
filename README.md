# Customer Retention & Acquisition Analysis | Power BI

> **Business question:** Adventure Works wins new customers but loses too many after their first purchase. Who are the new customers, how long do they stay, and how many more can we expect to acquire next year?

<img width="1368" height="684" alt="01-overview" src="https://github.com/user-attachments/assets/46c0b2a5-5886-46a6-ad66-d676765a5a35" />

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

# Detailed insights by report page

## Cohort analysis: first purchases

<img width="1367" height="693" alt="02-first-purchase" src="https://github.com/user-attachments/assets/31606fbc-f054-4be3-9930-c5cd6df02642" />

- **June 2022** was the best month of 2022 for new customers, with **933** first-time buyers. A spike like this suggests a successful campaign or a seasonal effect.
- **4,931** customers made their first purchase between December 2021 and December 2022.

## Customer retention over time

<img width="1369" height="692" alt="03-retention-over-time" src="https://github.com/user-attachments/assets/4ac59ed2-4511-4b3a-81f5-0d00a1d63b9a" />

- **621** customers of the **December 2021** cohort bought again in month 6.

## Customer retention rate

<img width="1368" height="694" alt="04-retention-rate" src="https://github.com/user-attachments/assets/552092ce-a268-4c62-a68b-d29f7128bf97" />

- The **December 2021** cohort is the largest, with **946** new customers, probably helped by holiday shopping and promotions.
- Retention of that cohort: **66%** in month 6 (June 2022), **60%** in July, **54%** in August and **43%** by December 2022. The month-6 peak may reflect seasonality (summer is peak season for cycling and outdoor gear) or a June promotion, which Adventure Works should verify.
- After **3 months**: **39%** for the December 2021 cohort versus **24%** for January 2022.
- **Reading:** customers acquired in peak season show stronger loyalty than those acquired in quiet months. Adventure Works should compare the experience of both cohorts (offers, channels, products) before drawing conclusions.

## Decomposition tree

<img width="1369" height="688" alt="05-decomposition-tree" src="https://github.com/user-attachments/assets/725736e9-bf55-41ba-9772-dffefe7cdfd9" />

- **Why it helps:** root-cause exploration without writing queries; it reveals concentration hidden behind balanced totals (the three regions look similar at the top level, but a strong skew appears after drilling down); it compares the weight of each category at every level; and users can reorder dimensions live in a meeting.
- **What it found:** a strong skew toward **women buying Road Bikes through retail stores in Asia**. Retail stores represent about **78%** of first purchases in that segment, and Accessories are the weakest category (25,870 in Asia).
- **Use for decisions:** target campaigns, retail partnerships and stock; check whether the high-volume entry path also retains well, then scale acquisition (if retention is strong) or fix post-purchase follow-up (if it is weak).

## Forecast of first purchases

<img width="1366" height="687" alt="06-forecast" src="https://github.com/user-attachments/assets/3140633f-53ab-48a3-a6af-8e20083ddf81" />

- About **919** new customers expected in **April 2023**, after a period of decline in the preceding months.
- About **223** new customers expected in **December 2023**.
- The confidence interval widens with the horizon: the further ahead, the less certain the projection, so plans should use the lower and upper bounds, not only the central line.

## Conclusion
The analysis gives management a view of when customers drop off, who the new customers are, and what acquisition may look like over the next 12 months, so that resources can be aligned with seasonality and market demand.


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
| <img width="700" height="300" alt="04-retention-rate" src="https://github.com/user-attachments/assets/211905df-9467-429b-910a-85b747b63bcc" />|
| <img width="700" height="300" alt="05-decomposition-tree" src="https://github.com/user-attachments/assets/5a7fd9b5-f3c8-4502-96fc-92c945ac3b0d" />|
| <img width="700" height="300" alt="06-forecast" src="https://github.com/user-attachments/assets/2b6cbe94-c68f-4bf8-adec-3e24cc2fd30f" />|

## Method

1. **Accessible theme:** *Accessible City Park* for readable contrast.
2. **Data preparation:** typed and formatted fields (date as month and year, currency with 2 decimals, region as geographic category).
3. **Cohort definition:** a calculated column assigns each customer to the month of their first purchase (`First Purchase Date`).
4. **Retention measures:** a `Months After Purchase` table (1 to 12) and two DAX measures, `Customer Retention` and `Customer Retention Rate %`.
5. **Exploration:** decomposition tree on `First Purchase Date` explained by region, gender, product and customer segment.
6. **Forecast:** Power BI forecasting on distinct new customers per month, 12 months ahead.

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
