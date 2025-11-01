# Sales-Performance-Analytics-using-Tableau
This project was for the Principle of Business Analytics module at Maynooth University (2025). Project includes detailed report and presentation on Sales Performance Analysis, THis is a business/data analytics project using Tableau and Excel
## 1) Project Overview
This project analyzes multi-year sales data to understand revenue, profit, discount impact, product mix, and regional performance.  
I cleaned the data, created calculated fields in Tableau, and built dashboards for decision support.  
Key business questions:
- Which categories and sub-categories drive most revenue and profit?
- Where do discounts reduce margin?
- Which regions and segments perform best over time?

## 2) Key Findings & Insights
-Sales, orders, customers, and profit grow every year from 2011 to 2014, with peak in 2014.
-Technology category contributes the most sales (≈36%) vs. Furniture and Office Supplies.
-West region shows highest revenue (~$730K) and profit (~$108K); Central has lowest profit.
-Phones sub-category is top in sales (~14.34% of total); Fasteners/Labels/Envelopes are minimal.
-Higher discounts often mean lower profit margin (e.g., Supplies, Machines). Pricing/discount review is needed.

## 3) Data & Cleaning
- Original dataset has: Order ID, Order Date, Ship Date, Customer, Segment, Region, Category, Sub-Category, Product, Sales, Quantity, Discount, Profit.
- Cleaning steps:
  - Removed duplicates and empty rows.
  - Standardized dates and category names.
  - Rounded incorrect fractional quantities.
  - Dropped `Country` because all values were the same.
- Basic descriptive stats were reviewed (sales, discount, profit) and outliers kept to reflect real conditions.

## 4) Tableau Modeling
**Hierarchies**
- Product: Category → Sub-Category → Product
- Customer: Customer ID → Segment
- Order: Order ID → Order Date
- Geography: Region

**Calculated Fields (examples)**
- `Profit Margin = [Profit] / [Sales]`
- `Profit per Unit = [Profit] / [Quantity]`
- `Previous Year Sales = LOOKUP(SUM([Sales]), -1)`
- `Above Avg Sales = SUM([Sales]) >= WINDOW_AVG(SUM([Sales]))`
- `Loss Flag = [Profit Margin] < 0`
- `Delivery Days = DATEDIFF('day',[Order Date],[Ship Date])`

  ## 5) Dashboards

1. **Performance Over Time**  
   Trends for Sales, Profit, Orders, and Customers by year and month.

2. **Category & Sub-Category Mix**  
   Contribution to sales and profit; identify top and low performers.

3. **Regional & Segment View**  
   Sales and profit by Region and Segment; highlight strong and weak areas.

4. **Discount vs Margin**  
   Relationship between discount levels and profit margin by sub-category.

## 6) How to Use

1. Open `tableau/workbooks/sales_performance.twbx` in Tableau Desktop or Tableau Public.  
2. If Tableau asks for data connection, point to `data/refined_data.xlsx`.  
3. Use filters for **Year**, **Segment**, **Region**, and **Category** to explore the dashboards.  
4. Export any dashboard image to `tableau/dashboards/` if you want to show previews on GitHub.

## 7) Business Recommendations

- **Pricing & Discount:** Reduce excessive discounts in low-margin sub-categories; monitor margin after changes.  
- **Product Mix:** Prioritize top performers (e.g., Phones, Chairs); review low-demand SKUs.  
- **Regional Focus:** Invest more in West; for Central, check logistics, discounting, and product–market fit.  
- **Seasonality:** Plan inventory and campaigns for strong months (for example, late-year peaks).

## 8) Files in /reports

- **Sales_Performance_Analysis_Report.pdf** — detailed write-up: cleaning, stats, calculations, and insights.  
- **Tableau report.pdf** — dashboard screenshots and KPI summaries.  
- **Presentation- Sales Performance Analysis.pptx** — slide deck for stakeholders.

## 9) Author
**Ashutosh Pathak**  
Business Analytics Student | Data Enthusiast  
ashup1033@gmail.com


