# Supply Chain Performance Analysis and Analytics
## 1. Executive Summary
This project analyzes the inventory performance of a liquor retail and distribution company using five operational datasets — Sales, Purchases, Invoices, Beginning Inventory, and Ending Inventory — to evaluate revenue concentration, supplier reliability, and stock efficiency.

Using Python (Jupyter) for Exploratory Data Analysis and classical inventory management formulas, the study assesses ABC classification, lead-time reliability, and inventory KPIs (Turnover, Days on Hand, Safety Stock, Reorder Point, and Target Level) under a 30-day review cycle.

In addition, an interactive Power BI dashboard was developed to visualize key KPIs and provide ongoing monitoring for operational teams.
  <img width="2320" height="1349" alt="image" src="https://github.com/user-attachments/assets/fe23df5b-d047-4e60-a1df-d9277f81e8fc" />
### Key insights:
* Strong Pareto pattern: A small share of items, stores, and vendors generate most revenue.
  * Top 10 items generate ~8 % of revenue.
  <img width="1928" height="658" alt="image" src="https://github.com/user-attachments/assets/28dfc282-53ea-46dc-b642-9a28151d3492" />
  * Top 10 vendors (7.7 % of base) supply 65.3 % of stock value.
  <img width="1790" height="647" alt="image" src="https://github.com/user-attachments/assets/65893679-4dad-42d1-9e39-ae911d559efb" />
  * Top 10 stores (12.5 % of network) create 37.7 % of revenue.
  <img width="1821" height="647" alt="image" src="https://github.com/user-attachments/assets/b6b82b1a-c696-4bc3-8fb2-394353ce4c3c" />
* Lead times average 7–8 days (max 14) for top vendors — predictable for planning; smaller vendors are volatile.
  <img width="1704" height="691" alt="image" src="https://github.com/user-attachments/assets/9beb0f26-0dc4-4c68-988b-82447f5dcf74" />
* Inventory misalignment: ~60 % of SKUs are in surplus, ~30 % in shortage, only ~11.5 % are optimal.
  <img width="1704" height="693" alt="image" src="https://github.com/user-attachments/assets/2ac12f30-8c77-4efc-911e-6b0a9dda2940" />
* Turnover is low–moderate (0.5–1.1×), and Days on Hand (50–150 days) remain high — excess capital locked in stock.
  <Figure size 1500x600 with 4 Axes><img width="1029" height="395" alt="image" src="https://github.com/user-attachments/assets/619e6215-c724-4968-8de7-bb32324d1fca" />
* Concentration risk: A few vendors dominate supply (e.g., DIAGEO NORTH AMERICA INC supplies 11,11% stock value).
  <img width="2292" height="1263" alt="image" src="https://github.com/user-attachments/assets/0970268b-c570-40ad-a896-1324a4e2e3e7" />

### So what:
The business can free up working capital and raise service levels by:
* Priritising A-category products, vendors, and stores.
* Rebalancing surplus vs. shortage stock.
* Consolidating vendor porfolios around reliable suppliers.
* Adjusting inventory across stores.
### References & Resources:
* Dataset: [Kaggle - Inventory Analysis Case Study](https://www.kaggle.com/datasets/bhanupratapbiswas/inventory-analysis-case-study)
* Full report (EDA notebook): [Jupyter Notebook](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb).
* Interactive dashboard: [Power BI (repo folder)](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard).
## Dataset Overview
The analysis uses five operational datasets from the [Kaggle - Inventory Analysis Case Study](https://www.kaggle.com/datasets/bhanupratapbiswas/inventory-analysis-case-study), representing real-world retail and distribution operations for a liquor company.

Each dataset captures a different part of the inventory cycle:
| Datasets | Description | Key Fields | 
| -------- | ------------ | ----------|
| Sales | Item-level transactions used to analyse revenue concentration and demand patterns. | InventoryId, SalesDate, SalesQuantity, SalesDollars,... | 
| Purchases| PO & receiving activity used for lead-time and supplier reliability checks. | InventoryId, PONumber, ReceivingDate, PurchaseAmount,...| 
| Invoices | Supplier & billing payments timing used to validate and evaluate vendors. | PONumbers, PODate, VendorNumber, Dollars,...| 
| Begining Inventory | Opening stock positions used for inventory metrics. | InventoryId, onHand, StartDate,....| 
| Ending Inventory | Closing stock positions used for inventory metrics. | InventoryId, OnHand, EndDate,...|

## Project Scope
The project aims to evaluate and explore chance to enhance inventory management efficiency of a liquor retail and distribution business through data-driven analysis. It focuses on understanding demand behavior, supplier performance, and stock alignment across brands, stores, and vendors.

Specifically, the analysis cover four key dimensions:
* ABC Classification – Segment liquor brands, and stores based on their contribution to total revenue, enabling targeted stock control and management focus.
* Lead Time Analysis – Measure supplier reliability and consistency by analyzing the time elapsed between purchase order placement and goods receipt.
* Inventory Efficiency – Assess stock performance using metrics such as inventory turnover, Days on Hand (DOH), safety stock, reorder points, and target levels to identify inefficiencies and capital constraints.
* Performance Analysis – Evaluate the best- and worst-performing items, stores, and vendors by combining sales, stock movement, and supplier data to pinpoint improvement opportunities.

The overall goal is to uncover operational inefficiencies that contribute to stockouts, overstocking, and high carrying costs, and to provide actionable recommendations for smarter procurement, optimized inventory levels, and improved financial performance.
## Methodology
1. Data preparation: Cleaning, validation, normalizsation (dates, units, vendor mapping)
2. Exploratory Data Analysis: Distribution, variability, stock status, vendor patterns
3. Quantitative methods:
   * ABC classification provides insights to prioritise focus areas.
   * Lead-time analysis informs vendor reliability and planning.
   * Inventory KPIs - turnover, DOH, safety stock, ROP, target level.
4. Visualisation and Reporting: Power BI dashboard Power BI dashboard for KPI tracking and store/vendor performance comparison.
5. Performance segmentation: Rank top and bottom brands, stores, and vendors.
## Analytics Insights
ABC Classification:
* A-items account for most value; B/C items numerous but low impact - focus management attention on A.
  <img width="1694" height="689" alt="image" src="https://github.com/user-attachments/assets/d462f7c5-6629-4947-9171-c08eba8daf6e" />
* Revenue is less concetrated at store level: A-stores generate ~80% of revenue; B and C stores contribute modestly.
  <Figure size 2100x750 with 2 Axes><img width="1336" height="470" alt="image" src="https://github.com/user-attachments/assets/eaa11ee2-64e7-4559-871d-029c7d9d9253" />
Lead Time:
* Average 7-8 days; A/B brands consistent - indicating opportunity to low buffer stock.
* Lower-tier brands show inconsistent delivery - requiring review for consolidation.
  <Figure size 1500x600 with 3 Axes><img width="971" height="395" alt="image" src="https://github.com/user-attachments/assets/b61a28ed-d227-48dc-9da6-bf6261fa4e9a" />
Inventory Structure:
* 60% surplus, 30% shortage, 11.5% optimal.
  <img width="1704" height="693" alt="image" src="https://github.com/user-attachments/assets/2ac12f30-8c77-4efc-911e-6b0a9dda2940" />
* High revenue items still exhibit imbalance - highlighting planning issue, not demand.
  <img width="1697" height="694" alt="image" src="https://github.com/user-attachments/assets/4f846b7e-5cea-4e6e-9eef-2cd79872f455" />
Performance:
* Top brands and stores dominate revenue but have low turnover - hinting capital inefficiency.
  <img width="1704" height="691" alt="image" src="https://github.com/user-attachments/assets/9beb0f26-0dc4-4c68-988b-82447f5dcf74" />
* Low performing stores contribute negligible value - implying candidates for cleanup.
  <img width="1800" height="691" alt="image" src="https://github.com/user-attachments/assets/f5fc76a9-f691-45c0-83fc-486ba81e35d3" />
## Power BI Dashboard
An interactive KPI dashboard is developed to complements the Python analysis to enable continuous monitoring. 

It visualises:
* Inventory turnover and DOH by store and brand.
* Surplus / shortage ratios.
* A item service level and stock status.
* Vendor lead time stability and on-time performance (OTIF)
* Comparative views for top vs bottom performers.
The dashboard provides real-time visibility for managers to track trends, investigate exceptions, and validate policy changes.
* Dymanic drill-through to a specific store/brand/vendor.

https://github.com/user-attachments/assets/5cb35376-53e4-4f47-9cff-84a08ceeb74c

## Assumptions and Limitations
Assumptions
* Fixed 30-day review cycle.
* Stable demand and lead times.
* Standard cost basis for valuation.
Limitation
* Historical data only; no forecasting or seasonality modelling
* Some incomplete vendor data.
* Review period not adjusted for category variability.
## Next Steps
* Recalibrate Safety Stock / Reorder Point / Target Levels on a quarterly cadence, using refreshed demand and lead-time data.
* Track core KPIs in the dashboard: Turnover, DOH, Inventory Status (surplus/shortage/optimal), Brand Availability, Lead-time Stability.
* Standardize data quality: proper date types, unit/size normalization, vendor mapping, lead-time completion.
* Rebalance inventory across stores before reordering to reduce excess and address shortages.
* EDA notebook (methods, visuals, metric formulas): [Link](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/blob/main/Liquor%20Inventory%20Analysis%20-%20A%20Case%20Study.ipynb)
* Power BI dashboard (interactive exploration): [Link](https://github.com/dukenguyen203-art/Liquor-Inventory-Analysis---A-Case-Study/tree/main/Dashboard)
## Author
Duke Nguyen
* Github: [@dukenguyen203-art](https://github.com/dukenguyen203-art)
* LinkedIn: [Duke Nguyen](https://www.linkedin.com/in/duke-n-nguyen/)
