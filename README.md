

# Data Analytics Power BI Report

In this project I:
- Performed ETL on a sample 120,000-record e-commerce data-set, extracting data
from Azure Storage and Azure SQL Database accounts into Power BI
- Transformed and cleaned data using Power Query to form a star-based
schema data model including a custom date table, and implemented 25 DAX
measures to support visualisations and time intelligence
- Created a 4-page report in Power BI containing 40 visualisations
- Constructed 5 SQL queries for the same data to generate insights for use
outside of the Power BI environment.

> Note: the customer data in this exercise is synthetic and doesn't actually represent real people.

### Step 1. Import Data
<div style="text-align: center"><img src="images\import.png" width=80%></img></div>

To simulate a real-world scenario, I imported data from a variety of data sources, including an Azure SQL DB, an Azure Blob Storage account, and web-hosted .csv files. I then performed data cleaning by removing irrelevant columns, splitting datetime details, concatenating other columns, maintaining data consistency and tidy naming conventions.

### Step 2. Build Data Model
<div style="text-align: center"><img src="images/data_model.png" width=80%></img></div>
I created a star-schema by centring the data around the `Orders` fact table,
and establishing one-to-many relationships with the various dimension tables.

This includes creating a date table from an M query, which dynamically chooses the fact table's earliest date as the start and the last as the end. This means as the data gets updated, so does the date table.

### Step 3. Customer Detail Page
<div style="text-align: center"><img src="images/customer_detail.png" width=100%></img></div>
I started with a page called `Customer Detail`, which focused on the organization's clientelle.

I included visuals with customer by country & by product category breakdowns. I then graphed the trend of the total customer count per month as well as forecasting, with seasonality in mind, into the future.

### Step 4. Executive Summary Page
<div style="text-align: center"><img src="images/exec_summary.png" width=100%></img></div>
This page is meant for the exec team of our fictional org, for a high-level overview of the company's performance. We have visuals for three quarterly KPIs, each with their own target calculations; some donut & bar charts to see the split between product category, country & store type revenue; and a line graph of the revenue trend, again with forecasting.


### Step 5. Product Detail Page
<div style="text-align: center"><img src="images/product_detail.gif" width=100%></img></div>
For this page, the focus was on hitting targets, the progress for which was displayed via the gauge visual, and tracking the most profitable and successful products.

I also began work on the navigation bar on the left of every page, in this case by adding a **slicer button**. This utilizes PowerBI's bookmarks feature to save several states of the report, hiding and unhiding visuals, and works neatly as a pop-out menu that would otherwise be cluttering the report.

### Step 6. Stores Map
<div style="text-align: center"><img src="images/stores_map.gif" width=100%></img></div>
Here, I set up a map visual showing us the various stores of the organization and their Profit Year-to-Date. This page also allows drilling-through individual stores to see them in extended detail, as well as a hover-tooltip to quickly see how the store is doing in regards to year-on-year targets, all calculated within the report.

### Step 7. Navigation Bar
<div style="text-align: center"><img src="images/nav_bar.gif" width=100%></img></div>
To aid with overall usability and UI consistency, I added navigation buttons to each of the pages.

### Step 8. SQL Queries
<div style="text-align: center"><img src="images/sql.png" width=100%></img></div>
As it is common in the industry for some colleagues or clients to not have direct access to visualisation tools like Power BI, I wrote 5 SQL queries to answer questions of varying complexity, ensuring these insights can still be extracted from the data and shared with a broader audience. You can find the `.sql` and extracted `.csv`s in the SQL folder of this repo.
<br>
I connected to the same DB with secure credentials via SQLTools in VSCode.