🍭 Candy Distribution Executive Performance Insights

📊 Business Overview

This project transforms raw transactional data from a National Candy Distributor into a 2-page interactive strategic dashboard. The goal is to provide the executive team with actionable insights into sales performance, factory efficiency, and Product performance.
✨ Key Deliverables
•	Executive Sales Overview: High-level tracking of Revenue, Profit, and Target Achievement.
•	Product & Factory Performance: Deep dive into manufacturing efficiency and product-mix profitability.
________________________________________

🏗️ Data Architecture (Star Schema)

To ensure high performance and scalability, I implemented a robust Star Schema model.
•	Fact Tables: Candy_Sales, Candy_Targets
•	Dimension Tables: Dim_Products, Dim_Factories, Dim_Calendar (DAX generated), uszips (Geographic mapping)
•	Bridge Logic: Leveraged the TREATAS DAX function to bridge the disconnected Targets table with the Sales engine without creating circular dependencies.
________________________________________

🧮 DAX Engineering

I built a centralized _Measures table organized into folders for maintainability. Key metrics include:
•	Target Achievement %: A dynamic gauge metric that tracks real-time progress against division-specific annual budgets.
•	YoY Sales Growth: Time-intelligence measures to compare current performance against the same period last year.
•	Factory Cost Efficiency: A calculated ratio measuring Sales ROI per unit of manufacturing cost.
•	Virtual Relationships:
Code snippet
Total Target = 
CALCULATE(
    SUM('Candy_Targets'[Target]),
    TREATAS(VALUES('Candy_Sales'[Division]), 'Candy_Targets'[Division])
)
________________________________________

🖥️ Dashboard Features

Page 1: Executive Overview
•	Strategic KPIs: Sales, Profit, and Margin tracking.
•	Trend Analysis: Dual-axis chart showing Revenue vs. Profit Margin over time.
•	Interactive Slicers: Global filters for Division.

Page 2: Product & Operational Performance
•	MVP: A Product summary depicting the "Star Products" (High Sales/High Margin).
•	Factory Efficiency: Visualizing profit contribution by manufacturing site.
•	AI Decomposition Tree: Root-cause analysis for profit variance.
•	Interactive Slicers: Global filters for Ship mode.

________________________________________

🛠️ Tools Used
•	Power BI Desktop: Report authoring and Data Modeling.
•	Power Query: Data cleaning (Trimming, Date formatting).
•	DAX: Advanced measures and time intelligence.
•	Excel/CSV: Raw data source files.

