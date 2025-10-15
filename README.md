# Liquor-Inventory-Analysis---A-Case-Study
## 1. Executive Summary
This project evaluates inventory performance for a liquor retail & distribution business using five operational datasets (sales, purchases, invoices, beginning and ending inventory). The analysis identifies revenue concentration, supplier reliability, and inventory misalignment, leveraging Python-based EDA and Power BI dashboarding.

**Key insights:**
* A small set of A-category brands and stores drive most revenue
* Lead time is stable for top vendors but volatile for others.
* ~ 60% of SKUs are in surplus, ~30% in shortage, and only ~11.5% optimal
* Turnover is low to morderate even for top sellers -> capital tied up in excess stock
* Dataset: [Kaggle - Inventory Analysis Case Study](https://www.kaggle.com/datasets/bhanupratapbiswas/inventory-analysis-case-study)
* Full report (EDA notebook): [Jupyter Notebook](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb) for detailed methodology and results.
* Interactive dashboard: [Power BI (repo folder)](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard) for interactive exploration
## 2. Project Background
The company operates multiple stores with a broad beverage portfolio but struggles with stockouts, overstocking, and high inventory costs. This project analyzes historical transactions to improve inventory planning via:
* ABC classificaltion of products and stores.
* Lead time reliability analysis to assess supplier performance and inventory planning.
* Inventory efficiency metrics: turnover, Days on Hand (DOH), surplus/shortage patterns.
* Strategic recommendations for working-captial optimization.

**So what:** Enable smarter procurement, lower carrying costs, and better service levels.
## 3. Data Structure (EDA Only)
The EDA phase used the five cleaned original operational data sets with no joins or modeling:

| Datasets | Description | Key Fields |
| -------- | ------------ | ----------|
| Sales | Item-level transactions used to analyse revenue concentration and demand patterns. | InventoryId, SalesDate, SalesQuantity, SalesDollars,... |
| Purchases| PO & receiving activity used for lead-time and supplier reliability checks. | InventoryId, PONumber, ReceivingDate, PurchaseAmount,...|
| Invoices | Supplier & billing payments timing used to validate and evaluate vendors. | PONumbers, PODate, VendorNumber, Dollars,...|
| Begining Inventory | Opening stock positions used for inventory metrics. | InventoryId, onHand, StartDate,....|
| Ending Inventory | Closing stock positions used for inventory metrics. | InventoryId, OnHand, EndDate,...|

Data cleaning (high level):
* Converting columns to proper data types (especially dates).
* Resolved missing or inconsistent vendor and item attributes.
* Standardized unit/size fields.
* Ensured referential consistency between VendorNumber keys across Purchases/Invoices.

Note: No data model was built at this stage—the focus was on dataset-level cleaning and exploratory insights.
## 4. Data Model for Dashboard (Built after EDA)
For the Power BI dashboard, the five datasets were normalized and reshaped into a 9-table multi-fact schema to enable fast, consistent slicing:
* **Fact tables**: Sales, Purchases, Inventory (snapshots from begining/ending), and Invoices
* **Dimentions**: Items (conformed), Brands, Stores, Vendors, and Date
<img width="1499" height="1018" alt="image" src="https://github.com/user-attachments/assets/a8d8ca7e-1094-4857-88f7-bfee2e155942" />
Modeling details:
* _Items_ is the central dimension, linking Sales, Purchase, and Inventory via _InventoryId_.
* Invoices connects to Purchases via _PONumber_.
* Date connects to Sales and Purchases through its respective date fields (_SalesDate_, _PurchaseDate_).
* Brands, Stoes, and Vendors provide filtering and grouping context.

Why this matters:
* Keep EDA lightweight and focused, while enabling a scalable BI-friendly star/snowflake model later.
* Ensure proper slicing across time, products, stores, and vendors without complex ad-hoc joins in Power BI.
## 5. Insights 
* **Revenue** concentration: A-category SKUs, top stores, and top vendors account for disproportionate share of results.
* **Vendor** performance: Lead times are stable for top vendors, with higher variability among lower-tier suppliers.
* **Inventory**–demand misalignment: Persistent surplus/shortage patterns tie up capital and risk missed sales.
* **Efficiency**: Turnover is generally low–moderate; many items exhibit high DOH despite strong revenue.
## 6. Next Steps
* Recalibrate Safety Stock / Reorder Point / Target Levels on a quarterly cadence, using refreshed demand and lead-time data.
* Track core KPIs in the dashboard: Turnover, DOH, Inventory Status (surplus/shortage/optimal), Brand Availability, Lead-time Stability.
* Standardize data quality: proper date types, unit/size normalization, vendor mapping, lead-time completion.
* Rebalance inventory across stores before reordering to reduce excess and address shortages.
* EDA notebook (methods, visuals, metric formulas): [Link](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb)
* Power BI dashboard (interactive exploration): [Link](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard)
## 7. Author
Duke Nguyen
* Github: [@dukenguyen203-art](https://github.com/dukenguyen203-art)
* LinkedIn: [Duke Nguyen](https://www.linkedin.com/in/duke-n-nguyen/)
