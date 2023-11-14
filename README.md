# games_store_analysis
Overview of a games store business performance
# Games Store Analysis
## Context
We are employed as Data Analysts for a gaming business with 349 brick & mortar stores nationwide. Business executives have asked us to provide them with dashboards showing how the business is performing to help them with business decisions. Executives have advised us that they don't have any dashboards currently and haven't provided us with any direction on what that they would like to be delivered. This is not an uncommon scenario in the real world, where a business unit doesn't have any dashboards or any reports that have been created. In these situations is upto us, as Data Analysts, to create these dashboards and reports. It's also not uncommon where you get some guidenace from stakeholders, but no further details on what report they would like specifically, which metrics they would like to see or any examples or mock ups of what they're after. Other times, you may get guidance from stakeholders, however as an **analyst**, it's upto you to understand the business, the business situation, what the stakeholders need, the best way to get it to them, anticipating what they might need down the track and preparing for it. 

## Business & Data Information
Here's the information we have on hand currently:
- The business launched on the 01/01/2020, assuming today is the 01/01/2023, we have we have 3 full years of data, with the last full day of data being 31/12/2023.
- The business sells video games and gaming systems, and operates as brick and mortar only with 349 stores nationwide
- We have been given 2 XLSX files aggregated to certain levels, with rather cryptic names. These files have been provided to us by the Data Engineering team, who have mentioned the data is clean and ready to work with in Tableau. 
  - [store_wbr_trans_data_20230424.xlsx](https://shorturl.at/dikmp) - This dataset contains store revenue, transactions and unit sales data, segmented by transaction date and store number. 
  - [sales_by_date_and_prod_cat.xlsx](https://shorturl.at/chGN4) - This dataset contans company-wide revenue, transactions and unit sales data, segemented by transaction date and product category. 

## Business Tasks
Here are our tasks as a Data Analyst based on the information provided.
1. Determine the key metrics
 - We need to provide stakeholders with important metrics to help with business decision making.
2. Provide double-click metrics
 - It's not enough just to provide key high level metrics such as total annual sales, we also need to provide the option to double-click into these metrics to allow stakeholders to see why sales are higher or lower.
3. Communicate metrics and other information accurately and effectively
 - We want to ensure we are providing professional looking and fully functioning dashboards. It's important to consider your target audience and any special requirements and catering to these e.g. vision requirements (colorblindness, sensitivity to certain colors, difficulty reading smaller text). We also want to focus on design elements such as colour, which should be used sparingly, shouldn't be too intense to maintain a relaxed and should be used with intention (reds for 'bad' or 'negativity' and greens for 'good' and positivity'). Other design elements include utilising white space to avoid cluttering and making sure objects are aligned to avoid distraction. 

- 
- S
- Thirdly
```sql
-- find names that are 'Peter'
  select
    c.customer id
  , c.name
  from
    customers c
  where
    name = 'Peter'

;
```
