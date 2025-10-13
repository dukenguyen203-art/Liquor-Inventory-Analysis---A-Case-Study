# Liquor-Inventory-Analysis---A-Case-Study
## 1. Executive Summary
This project evaluates inventory performance for a liquor retail and distribution business, using five operational datasets (sales, purchases, invoices, begining and ending inventory), THe analysis identifies revenue concentration, supplier reliability, and inventory misalignment, leveraging Python-based EDA and PowerBI dashboarding.

Key insights:
* A small set of A-category brands and stores drive most revenue
* Lead time is stable for top vendors but volatile for others.
* ~ 60% of SKUs are in surplus, ~30% in shortage, and only ~11.5% optimal
* Turnover is low to morderate even for top sellers -> capital tied up in excess stock

The original datasets can be downloaded [here](https://www.kaggle.com/datasets/bhanupratapbiswas/inventory-analysis-case-study)
See the [full report](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb) for detailed methodology and results.
Download the [Power BI dashboard](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard) for interactive exploration
## 2. Project Background
The company operates multiple stores with a broad beverage portfolio bu struggles with stockouts, overstocking, and high inventory costs. This project analyzes historical transactions to improve inventory planning through:
* ABC classificaltion of products and stores.
* Lead time reliability analysis to assess supplier performance and inventory planning
* Inventory efficiency metrics (turnover, days on hand, surplus/shortage patterns)
* Strategic performance analysis to guide working to guide working-captial optimization

So what: Enable smarter procurement, lower carrying costs, and better service levels.
## 3. Data Structure (EDA Only)
The EDA phase used the five cleaned original operational data sets with no joins or modeling:

| Datasets | Description | Key Fields |
| -------- | ------------ | ----------|
| Sales | Item-level transactions used to analyse revenue concentration and profile demand. | InventoryId, SalesDate, SalesQuantity, SalesDollars,... |
| Purchases| PO and receiving activity used for lead-time and supplier reliability checks. | InventoryId, PONumber, ReceivingDate, PurchaseAmount,...|
| Invoices | Supplier and billing payments timing used to validate and evaluate vendors. | PONumbers, PODate, VendorNumber, Dollars,...|
| Begining Inventory | Opening stock positions used for inventory metrics calculations. | InventoryId, onHand, StartDate,....|
| Ending Inventory | Closing stock positions used for inventory metrics calucaltions. | InventoryId, OnHand, EndDate,...|

Data cleaning during EDA included:
* Converting columns to proper data types (especially dates)
* Resolving missing or inconsitent data and vendor info
* Standardizing item and unit attributes
* Ensure referal consistency between PONumber and PONumber.

Note: No data model was built at this stage - the focus was on cleaning and exploratory insights per datasets.
## 4. Data Model for Dashboard (Built after EDA)
For the Power BI dashboard, the five datasets were normalized and reshaped into a 9-table multi-fact schema to enable fast, consistent slicing across processes:
* Fact tables: Sales, Purchases, Inventory (snapshot from begin/end), and Invoices
* Dimention: Items (conformed), Brands, Stores, Vendors, and Date
<img width="1499" height="1018" alt="image" src="https://github.com/user-attachments/assets/a8d8ca7e-1094-4857-88f7-bfee2e155942" />
Modeling details:
* _Items_ is the central dimension, linking Sales, Purchase, and Inventory via _InventoryId_.
* Invoices connects to Purchase via _PONumber_.
* Date connects to Sales and Purchases through its respective date fields (_SalesDate_, _PurchaseDate_).
* Brands, Stoes, and Vendors provide filtering and grouping context.

Why this matters:
* Keep EDA lightweight and focused, while enabling a scalable BI-friendly star/snowflake model later.
* Ensure proper slicing across time, products, stores, and vendors without complicated joins in Power BI.
## 5. Insights 
* Revenue is concentrated: A-category SKUs, top stores, and top vendors account for disproportionate share of results.
* Lead times are stables for top vendors, enabling predictable replenishment; variability is higher among lower-tier suppliers.
* Inventory is misaligned with demand: surplus/shortage patterns persist, tying up capital and risking missed sales.
* Turnover is generally low-morderate, with high Days on Hand, even for some high-revenue items.
## 6. Next Steps
* Recalibrate Safety Stock/ Reorder Point/ Target Level on a regular candence (e.g., quarterly) using refreshed demand and lead-time data
* Track core KPIs in the dashboard: Turnover, Days on Hand, Inventory Status, Brand Availability, and Lead Time stability.
* Standardize data quality (dates as dates, unit/size normalization, vendor mapping, lead-time completion).
* Rebalance inventory across stores before reordering to reduce excess and address shortages

Refer to the [EDA notebook](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb) for methodology, visuals, metric calculations, and insights analysis
Use the [Power BI dashboard](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard) for interactive exploration.
## 7. Author
Duke Nguyen
* Github: @dukenguyen203-art
* LinkedIn: [Duke Nguyen](https://www.linkedin.com/in/duke-n-nguyen/)







## 1. Project Background

This project analyzes inventory performance for a liquor retail and distribution business managing a diverse portfolio of alcoholic beverages across multiple store locations. The company faces recurring challenges with stockouts, overstocking, and high inventory carrying costs, impacting both revenue generation and working capital efficiency.

Using five core datasets (sales, purchases, invoices, beginning and ending inventory), the analysis identifies critical patterns in demand concentration, supplier reliability, and inventory alignment with actual sales. By applying ABC classification, lead time analysis, and inventory KPIs (turnover, Days on Hand, safety stock, reorder point, target level), the project uncovers structural inefficiencies and actionable improvement opportunities.

Insights and recommendations are provided in four key areas:

ABC Classification: Identify high-value items, stores, and vendors that drive the majority of revenue.

Supplier Performance: Evaluate lead time reliability and consistency.

Inventory Efficiency: Diagnose surplus vs. shortage patterns, turnover rates, and stock levels.

Strategic Planning: Recommend data-driven actions to optimize inventory and procurement strategy.

So what:
By targeting A-class items and reliable suppliers, rebalancing stock levels, and tightening planning processes, the business can unlock working capital, reduce carrying costs, and improve service levels, enabling more profitable and resilient operations.

* The original datasets can be downloaded here.
* The structured EDA Jupyter Notebook can be downloaded here.
* An interactive PowerBI dashboard can be downloaded here.

## Data Structure and Initial Check
