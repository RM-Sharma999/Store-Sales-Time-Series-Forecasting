# Store Sales Time Series Forecasting

Accurate sales forecasting helps retailers optimize inventory, reduce waste, and make informed decisions. This project uses the **Corporación Favorita Store Sales** dataset from Kaggle to analyze historical sales patterns and forecast future demand across product families. Through **exploratory data analysis(EDA)**, **feature engineering**, and **time series forecasting**, the project identifies key factors influencing sales performance and generates actionable forecasts.

---

## Objectives

* Analyze **historical sales trends** and **seasonal patterns**.
* Explore the impact of **promotions**, **holidays**, and other external factors on sales.
* Build and evaluate **time series forecasting models**.
* Forecast future sales across **product families**.
* Generate insights to support **data-driven retail planning**.

---

## Dataset

The dataset used in this project is the **Corporación Favorita Store Sales** dataset from the [Store Sales - Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting/overview). It contains historical sales data and insights on **stores**, **promotions**, **holidays**, **transactions**, and **oil prices**.

* **train.csv** – Historical sales data used for **analysis** and **model training**.
* **test.csv** – Data for the forecast period with **no sales values**.
* **stores.csv** – Metadata describing **store characteristics**.
* **oil.csv** – Daily **oil prices**, an external economic indicator.
* **holidays_events.csv** – Information on **holidays** and **special events**.
* **transactions.csv** – Daily **transaction counts** for each store.

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

### Product Family Sales Patterns (Mid & High-Volume)
The time series plots for mid and high-volume product families reveal strong weekly seasonality with prominent weekend spikes. Grocery I clearly dominates with the highest daily sales (often exceeding 400k units), followed by Beverages, Produce, and Cleaning. Other families like Poultry, Dairy, and Bread/Bakery show moderate volumes, while lower-volume categories (not shown here) tend to be more volatile. Occasional zero-sale periods indicate missing data or closures that should be addressed in preprocessing for robust forecasting.

<table>
  <tr>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/05cd07e1-4dc5-43d6-bfea-3a261a29699a" width="100%">
      <br>
      <b>Mid-Volume Product Family</b>
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/00b28ab5-d712-41f9-bd4f-fefd34ad3463" width="100%">
      <br>
      <b>High-Volume Product Family</b>
    </td>
  </tr>
</table>

### Weekly Pattern
The bar chart shows a strong weekly seasonality in sales. Weekends dominate with the highest average sales on Sunday (~460) and Saturday (~430), while weekdays are lower, with Thursday recording the lowest (~280). This clear weekend spike is a key pattern that should be accounted for in time series forecasting models.

<img width="552" height="521" alt="image" src="https://github.com/user-attachments/assets/ba22483e-c9b6-4f8b-b4d5-6a0482b76124" />

### Promotion Impact
The plot shows a strong positive impact of promotions on sales. Promotional days have significantly higher sales volumes and wider distribution compared to non-promotional days. While non-promotion days mostly record low sales, promotions frequently drive much larger volumes (with some outliers). This confirms promotions as a critical feature for time series forecasting models.

<img width="876" height="547" alt="image" src="https://github.com/user-attachments/assets/4bafec56-2a3f-4656-baa7-b910e8b8dfa1" />

---

## Modeling
Two separate modeling approaches were implemented using Prophet for store sales forecasting:

* **Baseline Model**: Utilized **date**, **product family**, and **holiday effects** (generated using the `holidays` Python library) to capture trends, seasonality, and holiday impacts.
* **Advanced Model**: Developed separately with richer feature engineering, incorporating **promotions**, **store_nbr**, and additional data from stores, transactions, and oil price dataframes. This enabled the model to account for store-specific behavior and external economic factors.

---

## Forecasting
Forecasts were generated for the test period using both **Baseline** and **Advanced** Prophet models. Below are sample future sales forecasts for the **Beverages** product family:

### Baseline Model
The **Baseline Model** was able to capture the general trend and weekly seasonality but showed limitations in handling sudden drops and promotional effects.

<img width="886" height="555" alt="image" src="https://github.com/user-attachments/assets/996ba821-5fc6-4b72-a5fe-1fb41e5be1f5" />

### Advanced Model
The **Advanced Model** produced more accurate and stable forecasts by better incorporating promotions, store-specific patterns, and external factors.

<img width="1034" height="547" alt="image" src="https://github.com/user-attachments/assets/86fafa2f-4df8-4d62-a8ee-63093326110c" />

---

## Results
The **Advanced Model** significantly outperformed the **Baseline Model** by delivering more accurate forecasts, particularly for high-volume families. As shown in the plot below for Beverages, it better captured promotional spikes, weekly seasonality, and store-level variations through the inclusion of `promotions`, `store_nbr`, and external data (stores, transactions, and oil prices), while the Baseline Model struggled with volatility.

<img width="1031" height="470" alt="image" src="https://github.com/user-attachments/assets/c61de545-6310-43cb-87c8-0a1912d2c58e" />

---

## Conclusion
This project demonstrates that while a **Baseline** Prophet model using `date`, `product family`, and `holidays` captures core trends and seasonality effectively, the **Advanced Model** significantly improves forecasting accuracy by incorporating `promotions`, `store_nbr`, and external data sources.
