# Store Sales Time Series Forecasting

Accurate sales forecasting helps retailers optimize inventory, reduce waste, and make informed decisions. This project uses the Corporación Favorita Store Sales dataset from Kaggle to analyze historical sales patterns and forecast future demand across product families. Through exploratory data analysis, feature engineering, and time series forecasting techniques, the project identifies key factors influencing sales performance and generates actionable forecasts.

---

## Objectives

* Analyze historical sales trends and seasonal patterns.
* Explore the impact of promotions, holidays, and other external factors on sales.
* Build and evaluate time series forecasting models.
* Forecast future sales across product families.
* Generate insights to support data-driven retail planning.

---

## Dataset

The dataset used in this project is the **Corporación Favorita Store Sales** dataset from the [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview). It contains historical sales data and insights on stores, promotions, holidays, transactions, and oil prices.

* **train.csv** – Historical sales data used for analysis and model training.
* **test.csv** – Data for the forecast period with sales values removed.
* **stores.csv** – Metadata describing store characteristics.
* **oil.csv** – Daily oil prices, an external economic indicator.
* **holidays_events.csv** – Information on holidays and special events.
* **transactions.csv** – Daily transaction counts for each store.

---

## Methodology

* Data Cleaning & Preparation
* Exploratory Data Analysis (EDA)
* Feature Engineering
* Time Series Forecasting with Prophet
* Model Evaluation
* Future Sales Prediction

---

## Exploratory Data Analysis (EDA)

Exploratory Data Analysis was performed to uncover sales patterns, understand demand behavior across product families, and evaluate factors that influence store sales. The analysis examined seasonality, promotions, holidays, customer transactions, and oil prices to identify trends and relationships that could improve forecasting performance.

### Total Sales Over Time
Total sales show a clear upward trend from 2013 to 2017, indicating overall business growth. Regular fluctuations suggest strong seasonal patterns and recurring demand cycles, making time series forecasting an appropriate approach for predicting future sales.

<img width="981" height="441" alt="image" src="https://github.com/user-attachments/assets/6c779685-2d61-41cd-a6be-cea1c2aaf99d" />

### Total Sales by Family
The bar chart shows the total sales volume across different product families. Grocery I is the clear leader with over 340 million units sold, followed by Beverages (~230M) and Produce (~140M), while many categories like Books, Baby Care, and Hardware contribute negligibly.

<img width="1040" height="700" alt="image" src="https://github.com/user-attachments/assets/b9adb55d-c800-44a0-ae88-884113aa92fc" />

### Product Family Sales Patterns (Low/Mid/High together)
<img width="800" height="470" alt="image" src="https://github.com/user-attachments/assets/00b28ab5-d712-41f9-bd4f-fefd34ad3463" />
<img width="791" height="470" alt="image" src="https://github.com/user-attachments/assets/05cd07e1-4dc5-43d6-bfea-3a261a29699a" />


Weekly Pattern
Promotion Impact
Transactions vs Sales
