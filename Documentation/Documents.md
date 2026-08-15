# 📊 Supply Chain Sales & Inventory Analytics | Power BI

![Power BI](https://img.shields.io/badge/Power%20BI-Business%20Intelligence-yellow)
![DAX](https://img.shields.io/badge/DAX-Analytics-blue)
![Power Query](https://img.shields.io/badge/Power%20Query-ETL-green)
![Excel](https://img.shields.io/badge/Excel-Data%20Source-brightgreen)

## Project Overview

**Supply Chain Sales & Inventory Analytics** is an interactive Power BI Business Intelligence project designed to provide an end-to-end view of sales, customers, products, suppliers, procurement, inventory, warehouses, shipments and returns.

The project connects the major business processes:

> **Sales → Procurement → Inventory → Shipment → Returns**

The objective is to transform operational data into meaningful KPIs, trends and business insights for management decision-making.

---

## 🎯 Business Problem

Supply-chain organizations generate data across multiple functions such as sales orders, customers, products, suppliers, purchase orders, inventory, warehouses, shipments and returns.

When these datasets are analyzed separately, it becomes difficult to answer questions such as:

- How much total sales and profit are being generated?
- Which customers and products drive the most revenue?
- Which suppliers and countries have the highest purchasing cost?
- How many purchase orders are completed, pending or cancelled?
- What is the current inventory value?
- Which warehouses hold the most stock?
- Is stock above or below reorder and safety-stock levels?
- How many shipments are delivered, delayed, in transit or cancelled?
- What are the main reasons for product returns?
- Which shipping modes are used most frequently?
- How can purchasing, inventory and logistics performance be improved?

This Power BI solution provides a centralized analytical view of these business areas.

---

## 🎯 Objectives

1. Monitor overall sales and profit performance.
2. Analyze customers, products, categories and cities.
3. Track purchase orders and procurement cost.
4. Evaluate supplier performance and supplier ratings.
5. Monitor warehouse stock and capacity.
6. Track inventory value, closing stock, reorder level and safety stock.
7. Analyze shipment status and shipment cost.
8. Identify return reasons and refund amounts.
9. Monitor monthly sales, profit, stock and return trends.
10. Support data-driven supply-chain decisions.

---

# 🧩 Data Model

The dashboard uses a dimensional structure containing dimension tables and fact tables.

### Dimension Tables

- `dim_Suppliers`
- `dim_Products`
- `dim_Customers`
- `dim_Warehouses`
- `Calendar`

### Fact Tables

- `fact_Sales_Orders`
- `fact_Purchase_Orders`
- `fact_Inventory`
- `fact_Shipments`
- `fact_Returns`

### Model Design

The dimension tables provide descriptive attributes while fact tables contain transactional/business measures.

Examples:

- Customers → Sales Orders
- Products → Sales Orders / Purchase Orders / Inventory
- Suppliers → Purchase Orders
- Warehouses → Inventory / Shipments
- Calendar → time-based analysis

The model is designed to support filtering and cross-analysis across sales, procurement, inventory, shipment and returns.

---

# 🧹 Data Preparation

Data preparation can be performed using **Power Query**.

Typical transformation steps include:

- Removing duplicate records
- Handling missing values
- Correcting data types
- Standardizing text fields
- Validating dates
- Cleaning categorical values
- Preparing numeric columns
- Checking relationships and key columns
- Creating an analysis-ready dataset

---

# 📊 Dashboard Pages

The report contains four main analytical sections.

## 1. Main Dashboard

### KPIs

- Total Sales
- Total Orders
- Total PO
- Total Profit
- Purchase Cost

### Visuals

- Sales & Profit Trend by Month
- Purchase Cost by Supplier / Country
- Sales by Region / Customer City
- Top 5 Sales by Supplier
- Top 5 Sales by Warehouse

### Filters

- Year
- Month
- City

### Purpose

Provides an executive-level overview of sales, profitability, procurement and geographic performance.

---

# 💰 2. Sales & Product Analysis

### KPIs

- Total Sales
- Total Discount
- Total Units Sold
- Total Customers
- Average Order Value

### Visuals

- Top 10 Customers
- Sales by City
- Sales by Category
- Top 5 Sales Products

### Business Questions

- Who are the highest-value customers?
- Which products generate the most sales?
- Which cities perform best?
- Which categories contribute most to revenue?

---

# 🏭 3. Warehouse & Purchase Orders

### KPIs

- Total PO
- Total Warehouses
- Inventory Value
- Total Capacity
- Supplier Rating

### Visuals

- PO Status
- Top 5 PO Suppliers
- Closing Stock Trend
- Warehouse Stock Status Table

### Stock Metrics

- Opening Stock
- Received Quantity
- Sold Quantity
- Closing Stock
- Reorder Level
- Safety Stock

### Business Questions

- Which suppliers receive the most purchase orders?
- What is the inventory value?
- Which warehouses hold the most stock?
- Is stock approaching reorder levels?
- How is stock changing month by month?

---

# 🚚 4. Return & Shipment Analysis

### KPIs

- Total Return
- Order Quantity
- Total Refund
- Total Shipment
- Shipment Cost

### Visuals

- Orders Return Reason
- Shipment Status
- Orders Return Trend by Month
- Shipping Mode

### Shipment Status

- Delivered
- In Transit
- Delayed
- Cancelled

### Return Reasons

- Quality Issue
- Late Delivery
- Wrong Item
- Defective
- Damaged
- Not Required
- Size Issue

### Business Questions

- Why are orders being returned?
- How many shipments are delayed?
- Which shipping mode is used most?
- What is the monthly return trend?
- How much refund is being generated?

---

# 🔍 Key Business Insights

Based on the dashboard visuals:

### Sales & Profit

Sales performance can be compared with profit to understand whether revenue growth is translating into profitability.

### Customers

Top-customer analysis helps identify high-value accounts that can be prioritized for retention and relationship management.

### Products

Top-product and category analysis helps identify products that contribute significantly to revenue.

### Suppliers

Supplier and country analysis highlights where procurement spend is concentrated and can support supplier evaluation.

### Inventory

Warehouse stock analysis provides visibility into opening stock, received quantity, sold quantity, closing stock, reorder level and safety stock.

### Shipments

Shipment status provides visibility into delivered, in-transit, delayed and cancelled orders.

### Returns

Return-reason analysis can identify recurring quality, delivery or product-related problems.

### Logistics

Shipping-mode analysis supports decisions around transportation planning and logistics cost.

---

# 💡 Business Recommendations

### Sales

- Prioritize high-value customers.
- Focus on high-performing products and categories.
- Investigate underperforming cities.
- Monitor revenue and profit together.

### Procurement

- Compare supplier purchase cost and supplier rating.
- Negotiate with high-spend suppliers where appropriate.
- Monitor purchase-order status.

### Inventory

- Use reorder levels and safety stock to reduce stock-out risk.
- Avoid unnecessary excess inventory.
- Monitor warehouse-level stock movement.

### Logistics

- Investigate delayed and cancelled shipments.
- Compare shipping modes based on cost and service performance.
- Improve delivery planning.

### Returns

- Investigate repeated return reasons.
- Improve product quality and packaging where required.
- Reduce avoidable delivery and wrong-item returns.

---

# 🧮 Example DAX Measures

> Exact table/column names may vary depending on the final Power BI model. The following are industry-standard examples based on the fields visible in the model.

### Total Sales

```DAX
Total Sales =
SUM(fact_Sales_Orders[Sales_Amount])
```

### Total Profit

```DAX
Total Profit =
SUM(fact_Sales_Orders[Profit])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(fact_Sales_Orders[Order_ID])
```

### Total Units Sold

```DAX
Total Units Sold =
SUM(fact_Sales_Orders[Quantity])
```

### Total Discount

```DAX
Total Discount =
SUM(fact_Sales_Orders[Discount])
```

### Total Purchase Cost

```DAX
Total Purchase Cost =
SUM(fact_Purchase_Orders[Purchase_Cost])
```

### Total Purchase Orders

```DAX
Total PO =
DISTINCTCOUNT(fact_Purchase_Orders[Purchase_ID])
```

### Total Shipment

```DAX
Total Shipment =
DISTINCTCOUNT(fact_Shipments[Shipment_ID])
```

### Shipment Cost

```DAX
Shipment Cost =
SUM(fact_Shipments[Shipping_Cost])
```

### Total Refund

```DAX
Total Refund =
SUM(fact_Returns[Refund_Amount])
```

### Total Returns

```DAX
Total Returns =
DISTINCTCOUNT(fact_Returns[Return_ID])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Sales], [Total Orders])
```

### Closing Stock

```DAX
Closing Stock =
SUM(fact_Inventory[Closing_Stock])
```

### Inventory Value

```DAX
Inventory Value =
SUMX(
    fact_Inventory,
    fact_Inventory[Closing_Stock] *
    RELATED(dim_Products[Selling_Price])
)
```

> Update the product-price column if the final model uses a different field.

---

# 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Power BI | Dashboard and visualization |
| Power Query | Data cleaning and transformation |
| DAX | Measures and KPIs |
| Excel | Data source / dataset |
| Data Modeling | Relationships and analytical structure |
| Data Visualization | Business reporting |

---

# 📈 Dashboard Features

- Interactive KPI Cards
- Year / Month / City slicers
- Sales trend analysis
- Profit trend analysis
- Customer analysis
- Product analysis
- Category analysis
- Supplier analysis
- Purchase-order analysis
- Warehouse analysis
- Inventory analysis
- Shipment analysis
- Return analysis
- Geographic sales visualization
- Drill-down / filtering through report interactions

---

# 📁 Recommended GitHub Structure

```text
Supply-Chain-Sales-Inventory-Analytics-PowerBI/
│
├── README.md
│
├── PowerBI/
│   └── Supply_Chain_Sales_Inventory_Analytics.pbix
│
├── Dataset/
│   └── Supply_Chain_Data.xlsx
│
├── Dashboard_Screenshots/
│   ├── 01_Data_Model.png
│   ├── 02_Main_Dashboard.png
│   ├── 03_Sales_Product.png
│   ├── 04_Warehouse_PO.png
│   └── 05_Return_Shipment.png
│
├── Documentation/
│   ├── Project_Overview.md
│   ├── Data_Model.md
│   ├── Data_Cleaning.md
│   ├── DAX_Measures.md
│   └── Business_Insights.md
│
├── Presentation/
│   └── Supply_Chain_Sales_Inventory_Analytics_Presentation.pptx
│
└── LICENSE
```

---

# 🚀 How to Use

1. Download or clone the repository.
2. Open the `.pbix` file using Power BI Desktop.
3. Update the dataset source path if required.
4. Refresh the data.
5. Use the Year, Month and City filters.
6. Navigate between Main, Sales, Warehouse & PO and Return & Shipment pages.
7. Interact with the visuals to perform detailed analysis.

---

# 🔮 Future Improvements

- Sales forecasting
- Profit margin analysis
- Supplier performance scorecard
- Inventory forecasting
- Stock-out prediction
- Customer segmentation
- ABC inventory analysis
- Delivery-time analysis
- Return-rate KPI
- Automated data refresh
- Target vs Actual analysis
- Advanced logistics cost optimization

---

# 💼 Resume-Ready Description

**Supply Chain Sales & Inventory Analytics | Power BI**

- Developed an interactive Power BI dashboard to analyze **sales, customers, products, suppliers, purchase orders, inventory, returns and shipments**.
- Built a dimensional data model and DAX-driven KPIs for **revenue, profit, orders, purchase cost, inventory value, shipment cost, refunds and customer performance**.
- Created interactive analysis for **sales trends, top customers/products, supplier procurement, warehouse stock, shipment status and return reasons**.
- Generated business insights to support **inventory planning, supplier evaluation, customer prioritization, logistics optimization and return reduction**.

---

# 🧑‍💻 Skills Demonstrated

```text
Power BI
DAX
Power Query
Excel
Data Cleaning
Data Transformation
Data Modeling
Business Intelligence
Sales Analytics
Customer Analytics
Inventory Analytics
Supply Chain Analytics
Procurement Analytics
Logistics Analytics
Data Visualization
KPI Development
Business Analysis
```

---

# 🏷️ Recommended GitHub Topics

```text
power-bi
powerbi-dashboard
data-analysis
business-intelligence
dax
power-query
data-modeling
supply-chain-analytics
sales-analysis
inventory-analysis
procurement
warehouse-analytics
logistics-analytics
customer-analysis
product-analysis
shipment-analysis
data-visualization
kpi-dashboard
business-analytics
data-analyst
```

---

# 📌 GitHub Repository Name

**`Supply-Chain-Sales-Inventory-Analytics-PowerBI`**

### GitHub Description

> Interactive Power BI dashboard for analyzing supply-chain sales, customers, products, suppliers, procurement, inventory, warehouses, shipments and returns.

---

# 👨‍💻 Author

**Pranit Pawar**

**Data Analyst | Power BI | Excel | SQL | Data Visualization**

---

## ⭐ Project Highlights

This project demonstrates practical experience in:

- Business Intelligence
- Data Cleaning
- Data Transformation
- Data Modeling
- DAX
- Power BI Dashboard Development
- Sales Analytics
- Procurement Analytics
- Inventory Analytics
- Warehouse Analytics
- Customer Analytics
- Shipment Analytics
- Return Analytics
- KPI Development
- Business Insights
- Data-Driven Decision Making

---

## 📜 License

This project is intended for portfolio and educational purposes.

If the underlying dataset contains confidential business information, do not publish the original data publicly.
