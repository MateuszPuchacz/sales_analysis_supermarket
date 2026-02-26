# sales_analysis_supermarket
Power BI sales performance dashboard based on two years of supermarket sales data, integrating custom data modeling, DAX measures, product level performance tracking, and profitability analysis within an interactive BI environment.


## 🎯 Project Goal

The goal of this project was to build a clear and business-focused Power BI sales dashboard based on two years of supermarket data (2021–2022).

The main objectives were:

- Monitor core KPIs such as Total Sales, Total Profit, and Profit %
- Compare performance between 2021 and 2022
- Analyze monthly and daily sales trends
- Identify top-performing products and categories
- Understand sales distribution by payment method and sales type
- The project focuses on clean data modeling, logical report structure, and business clarity rather than complex DAX logic because I had clear small dataset. The goal was to simulate a practical management dashboard used for operational monitoring and performance evaluation.



## 📊 Data Source

The dataset used in this project was simulated for educational and portfolio purposes.
It does not represent real company data.

The dataset consists of two primary tables: a transactional sales table and a product/category dimension table. 
It was synthetically generated to simulate a supermarket retail environment covering two years of operations.


## Sales (Fact Table)

Contains transaction-level sales records.
Each row represents a single sales transaction.

Key fields:

- Order ID – unique transaction identifier
- Order Date – transaction date
- Year – sales year (2021–2022)
- Month Name – month of transaction
- Sales Type – type of sale (Direct Sales)
- Payment Mode – payment method (Cash, Online)
- Product ID – product reference key
- Quantity – number of units sold
- Unit Price – selling price per unit
- Unit Cost – cost per unit
- Total Selling Value – total revenue per transaction
- Total Buying Value – total cost per transaction


This table serves as the analytical core for revenue, cost, profit, margin calculations, and time based analysis.

## Product (Dimension Table)

Contains descriptive product and category information.
Each row represents a unique product.

Key fields:

- Product ID – unique product identifier
- Product Name – product label used in reporting
- Category – product category classification

This table enables:

- Product performance ranking
- Category - level aggregation
- Top product and top category analysis
- Tree map visualization and segmentation

## 🛠 Tools & Technologies

**Excel**
Performed structured data validation, integrity checks, and preliminary preparation to ensure analytical readiness before integration into the BI model.

**Power BI**
Designed and implemented a relational data model (star schema approach), developed DAX measures for profitability and KPI tracking, and built an interactive executive level dashboard supporting performance analysis and decision making.

**AI Assisted Design (ChatGPT)**  
Generated visual branding assets (logo) for portfolio presentation purposes.


## 🧱🧹 Data Preparation & Modeling

**Excel – Data Quality Checks**

Before importing the dataset into Power BI, an initial validation step was carried out in Excel to review the structure and completeness of the data.
The following checks were performed:
Identification of missing values in key fields (Order Date, Total Selling Value, Total Buying Value, Quantity, Sales Type, Payment Mode).

Data type verification:

- Order Date formatted as Date
- Total Selling Value and Total Buying Value set as Decimal Number
- Quantity defined as Whole Number
- Order ID and Product ID stored as Text
- Logical consistency validation performed (no negative quantities, no inconsistencies between selling and buying values)

The objective was to ensure accurate and well-structured input data before developing the relational model and few DAX calculations in Power BI.


**Power BI – Data Transformation & Analytical Modeling**

Instead of creating a separate Date Table in DAX, time-related attributes were derived directly from the existing Date column to enable period-based analysis in visuals and slicers.

Created date attributes (Power Query):

Year
Month (number)
Month Name
Day (day of month)

This approach provided the necessary time context for filtering and trend analysis without adding an additional calendar table.

Core DAX Calculations (KPIs & Profitability)
Basic financial measures were created in DAX to support revenue, cost, and margin reporting:
```
- Total Buying Value = QUANTITY * MasterData.BUYING PRIZE
- Total Selling Value = QUANTITY * MasterData.SELLING PRICE * (1 - DISCOUNT %)
- Profit = Total Selling Value - Total Buying Value
- Profit % = Profit / Total Buying Value
```


## 🔗 ER Diagram

The data model consists of two tables connected by a one-to-many relationship.
MasterData stores product details (category, prices, UOM), while InputData contains transactional sales records.
The relationship ensures consistent product information across transactions and supports accurate sales and profit analysis.

![er_diagram](./images/er_diagram.png)











