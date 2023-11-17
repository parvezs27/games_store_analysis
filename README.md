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
1. Determine the key metrics to assist stakeholders with business decisions.
 - All businesses are concerned with revenue, so we will report revenue. But should the revenue be for the full 3 years of data? We can certainly get a high level look and a get a look at the broader trends occuring over 3 years and then drill down into annual, quarterly and monthly time periods. Stakeholders will be able to see annual data and compare it to other years, quarterely revenue also make sense as businesses tend to file their financials on a quarterely basis.  
2. Provide double-click metrics
 - It's not enough just to provide key high level metrics such as total annual sales, we also need to provide the option to double-click into these metrics to allow stakeholders to see why sales are higher or lower.
3. Communicate metrics and other information accurately and effectively
 - We want to ensure we are providing professional looking and fully functioning dashboards. It's important to consider your target audience and any special requirements and catering to these e.g. vision requirements (colorblindness, sensitivity to certain colors, difficulty reading smaller text). We also want to focus on design elements such as colour, which should be used sparingly, shouldn't be too intense to maintain a relaxed and should be used with intention (reds for 'bad' or 'negativity' and greens for 'good' and positivity'). Other design elements include utilising white space to avoid cluttering and making sure objects are aligned to avoid distraction.

## Building the Revenue Dashboard
For the sake of length and simplicity, we will not do a step by step walkthrough, but rather highlight anything key such as problems we run into during creation of the dashboard.

Problem 1. Null Date Values in Tableau

We have run into our first issue! Once we've connected to our data source and dragged the total revenue and transaction fields into our shelves, we can see that there's $1895 worth of revenue with no associated transaction dates.

![image](https://github.com/parvezs27/games_store_analysis/assets/107979122/b6c2c315-5331-4afc-b8d2-60b8a712adab)

Despite the data type being set to date in Tableau as highlighted above, we're still facing this problem. Lets take a closer look by using Tableau's view data feature, which will show us which rows the transaction date is showing as null. Right click null value > view data > full data > show fields > select all fields. 

![image](https://github.com/parvezs27/games_store_analysis/assets/107979122/4b2fc935-5cce-4fd4-969d-2e3ec47df034)

We can see above that there's two rows showing null transaction date values. There may be a formatting error or a typo in the data source leading to this, lets head over to our data source in Excel and find the above rows. We will utilise filters and custom text filters to find the two rows. Filtering by the 2 store names and entering the total revenue amounts of 168.39 and 1726.31 as custom text filters will help us get to the 2 rows. 

![image](https://github.com/parvezs27/games_store_analysis/assets/107979122/7e735347-172b-48ed-a78c-0c88cd9d1e2e)

The two rows are displayed above and we can see that the transaction dates are indeed there. So why are they showing as null in Tableau? This is due to one, of the many issues in Tableau, where despite the column format/data type is set to 'date' in Excel, some values don't get interpreted as dates once imported into Tableau. So how do we fix this? Changing the column format/data type to 'text' and then importing into Tableau will fix the issue. It's important we **do not change the original file** containing the original dataset, this is incase something goes wrong. We will first create a copy of the file, copy the transaction date column into notepad, paste it back into the desired in column in excel and set the column format/data type to 'text'. After doing this we will save the file to a secure location and use it as our new data source in Tableau. As we can see below, when the new transaction date column is used no null values are showing. 

![image](https://github.com/parvezs27/games_store_analysis/assets/107979122/9063e42a-554d-4d93-9e34-c11ad852f5de)

Below is a our revenue dashboard

link

Some quick mentions of what we did here
- We double checked the percent different calculations using a calculator to make sure the calculations were correct. It's not uncommon for calculations to not go as expected, so we always make sure to do our QA (quality assurance).
- We duplicated worksheets in order to avoid having to do things again and reduce the occurence of bugs.
- You can have the dollar signs in brackets, as it's good to have the units in brackets like KG or KM kilometers, but dollars in which country? Better to have if it's US dollars or Aus dollars, the dollar signs are already there
- documentation - dashboard documentation is extremely important. co-workers and stakeholders need to know who built it, who is maintaining it, why it was built and problem it's solving, what the refresh intervals are, how the metrics are calculated, what the metrics and charts say. We want to make life easier for our target audience, co-workers, stakeholders, and ourselves, time and efforts should be spent on productivity in other areas, rather than decoding the mystery of a dashboard without sufficient documentation.  audience needs to know what the data source is,  It's not enough to have.... usually you'll find a something like a text box containing information
- now if you have the docoumentation in the workbook, if you need to go back and change something, you'll have to find the dashboard, download it if it's not saved locally, make your changes and then re-publish, all whilst increasing your risk of messing something up such as the filters or any other elements of your dashbord. you'll have to create a backup copy too every time you want to make changes to the documentation, incase something goes wrong. having a block of text and unnecesarily take up space in the dashboard and affect the UI experience for the viewer. 
- Documentation placed inside the dashboard is also not searchable, in the real world where you might have dozens or hundreds of dashboards, if you need to find which dashboard uses a particular dataset or a particualr field, you'd have no idea. It's much more easier and time saving to have your documentation outside of dashboards.
- People often put an information "i" icon which you hover over, but not good as when you scroll down it's disappeared, you then have to scroll back up, not a good experience. Having it externally, allows you to have your dashboard side by side with the documentation which is a much better experience. that's why have a footer at the bottom of the page with a link leading to documentation, this could be stored on the companies internal page or on google drive .

- 





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
