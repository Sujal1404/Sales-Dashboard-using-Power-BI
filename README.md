# Sales Dashboard-using-Power-BI
The E-Commerce Business Intelligence Dashboard is an end-to-end data analytics project developed using Power BI to transform raw e-commerce data into meaningful business insights.
This dashboard helps stakeholders monitor sales performance, customer behavior, product trends, and operational efficiency through interactive visualizations and KPIs.

🎯 Project Objective

The main objective of this project is to:

Analyze sales and revenue trends

Identify top-performing products and categories

Track customer purchasing behavior

Monitor regional performance

Evaluate order fulfillment efficiency

Enable data-driven decision-making

🗂 Dataset Description

The dataset contains transactional e-commerce data with the following columns:

Order ID

Date

Status

Fulfilment

Sales Channel

ship-service-level

Style

SKU

Category

Size

ASIN

Courier Status

Qty

Currency

Amount

ship-city

ship-state

ship-postal-code

ship-country

promotion-ids

B2B

🛠 Tools & Technologies Used

Power BI Desktop

Power Query (Data Cleaning & Transformation)

DAX (Data Analysis Expressions)

Data Modeling

Interactive Dashboard Design

🔄 Project Workflow (End-to-End Process)
1️⃣ Data Collection

Imported raw e-commerce dataset (CSV/Excel format) into Power BI.

2️⃣ Data Cleaning (Power Query)

Removed duplicate Order IDs

Handled missing values

Standardized date format

Corrected data types

Created Year, Month, and Quarter columns

Removed unnecessary columns (if required)

3️⃣ Data Modeling

Created Date Table (Calendar Table)

Established relationships between:

Date → Orders

SKU → Product Data

Defined primary and foreign keys

Implemented star schema model

4️⃣ DAX Measures Created
💰 Revenue Measures
Total Revenue = SUM('Ecommerce'[Amount])

Total Orders = DISTINCTCOUNT('Ecommerce'[Order ID])

Total Quantity = SUM('Ecommerce'[Qty])

Average Order Value = DIVIDE([Total Revenue], [Total Orders])
📈 Growth Metrics
Monthly Revenue = CALCULATE([Total Revenue], 
                    DATESMTD('DateTable'[Date]))

Revenue LY = CALCULATE([Total Revenue], 
                SAMEPERIODLASTYEAR('DateTable'[Date]))

Revenue Growth % = 
DIVIDE([Total Revenue] - [Revenue LY], [Revenue LY])
📊 Dashboard Structure (3 Pages)
📄 Page 1: Sales Overview Dashboard
KPIs:

Total Revenue

Total Orders

Total Quantity Sold

Average Order Value

Visuals:

📊 Line Chart → Monthly Sales Trend

📊 Bar Chart → Sales by Category

🌍 Map → Sales by State

📦 Donut Chart → Sales Channel Distribution

📋 Table → Top 10 Products by Revenue

Slicers:

Date

Category

Sales Channel

State

📄 Page 2: Product & Customer Insights
KPIs:

Top Category Revenue

Top SKU Sales

B2B vs B2C Sales

Promotion Impact

Visuals:

📊 Bar Chart → Top 10 SKUs

📊 Column Chart → Category Performance

🍩 Donut Chart → B2B vs Non-B2B

📈 Line Chart → Promotion vs Non-Promotion Sales

📋 Matrix → Category & Size Performance

Slicers:

Promotion

Size

Category

Date

📄 Page 3: Operational & Regional Analysis
KPIs:

Delivered Orders

Cancelled Orders

Delivery Success Rate

Courier Performance %

DAX for Operational KPIs:
Delivered Orders = 
CALCULATE(COUNT('Ecommerce'[Order ID]),
'Ecommerce'[Status] = "Delivered")

Cancelled Orders = 
CALCULATE(COUNT('Ecommerce'[Order ID]),
'Ecommerce'[Status] = "Cancelled")

Delivery Success Rate % =
DIVIDE([Delivered Orders],
       [Delivered Orders] + [Cancelled Orders])

Courier Performance % =
DIVIDE(
    CALCULATE(COUNT('Ecommerce'[Order ID]),
              'Ecommerce'[Courier Status] = "Delivered"),
    COUNT('Ecommerce'[Order ID])
)
Visuals:

📊 Clustered Bar Chart → Orders by Status

🌍 Map → Orders by Region

📈 Line Chart → Monthly Delivery Rate

📊 Bar Chart → Courier Performance

📋 Table → State-wise Delivery Analysis

Slicers:

Courier Status

Fulfilment Type

Date

State

📌 Key Business Insights

Identified peak sales months

Determined best-performing product categories

Found high-revenue states

Analyzed impact of promotions

Improved understanding of delivery efficiency

Detected operational bottlenecks

🎨 Dashboard Design Features

Clean and professional theme

Consistent color palette

KPI cards with icons

Interactive slicers

Drill-through functionality

Tooltip pages for deeper insights

🚀 Business Impact

This dashboard helps:

✔ Management track revenue performance
✔ Marketing team analyze promotion effectiveness
✔ Operations team monitor delivery efficiency
✔ Sales team identify high-performing products
✔ Leadership make data-driven strategic decisions

📂 Repository Structure
📁 E-Commerce-BI-Dashboard
 ┣ 📂 Dataset
 ┣ 📂 Dashboard Screenshots
 ┣ 📄 ECommerce_Dashboard.pbix
 ┣ 📄 README.md
