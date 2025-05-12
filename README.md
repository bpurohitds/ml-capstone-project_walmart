# ml-capstone-project_walmart

# Capstone Project: Walmart Sales Forecasting

## Table of Contents
1. [Problem Statement](#1-problem-statement)  
2. [Project Objective](#2-project-objective)  
3. [Data Description](#3-data-description)  
4. [Data Preprocessing & EDA](#4-data-preprocessing--eda)  
5. [Model Selection](#5-model-selection)  
6. [Model Motivation](#6-model-motivation)  
7. [Assumptions](#7-assumptions)  
8. [Model Evaluation](#8-model-evaluation)  
9. [Key Insights](#9-key-insights)  
10. [Future Scope](#10-future-scope)  
11. [Conclusion](#11-conclusion)  
12. [References](#12-references)  

---

## 1. Problem Statement
Walmart is facing challenges in forecasting weekly sales for each of its stores, affecting inventory management. The goal is to build a predictive model that accurately forecasts sales for the next 12 weeks, improving operational efficiency and decision-making.

---

## 2. Project Objective
- Analyze Walmart's historical sales data.
- Identify patterns and influencing factors.
- Build a predictive model to forecast weekly sales for the next 12 weeks per store.

---

## 3. Data Description
Dataset includes:
- `Store`: Store ID  
- `Date`: Date of observation  
- `Weekly_Sales`: Sales for that week  
- `Holiday_Flag`: Holiday week indicator  
- `Temperature`: Regional temperature  
- `Fuel_Price`: Fuel price in the area  
- `CPI`: Consumer Price Index  
- `Unemployment`: Unemployment rate  

Descriptive stats show significant variance in weekly sales with minimal missing data.

---

## 4. Data Preprocessing & EDA
- Converted `Date` column to `datetime`
- Aggregated weekly sales to observe trends
- Identified top/worst performing stores (e.g., Store 20, Store 33)
- Performed seasonal decomposition and correlation analysis

**Correlation Highlights:**
- Unemployment: Moderate negative impact
- CPI & Temperature: Weak correlation with sales

---

## 5. Model Selection
Chosen Model: **SARIMAX** (Seasonal ARIMA with Exogenous Variables)  
Rationale:
- Handles seasonality effectively  
- Incorporates external factors like fuel price, CPI, etc.

---

## 6. Model Motivation
SARIMAX was selected due to:
- Strong support for seasonal trends  
- Flexibility in adding external variables  
- Historical success in retail time-series forecasting  

---

## 7. Assumptions
- Sales have seasonal patterns  
- Exogenous variables influence sales  
- Historical trends will persist over the forecast horizon

---

## 8. Model Evaluation
- Model fit using `statsmodels` SARIMAX
- Saved using `joblib`
- Forecasted next 12 weeks for each store
- Visualized confidence intervals
- Correlation & decomposition analyses performed

---

## 9. Key Insights
- **Unemployment:** Strongest negative impact in Stores 38 & 44  
- **Holidays:** Significant spikes observed  
- **Store 20:** Top performer  
- **Store 33:** Worst performer  
- **Seasonality:** Clear peaks, useful for planning

---

## 10. Future Scope
- Add variables like local promotions and competitor data  
- Explore advanced ML models (XGBoost, LSTM, etc.)  
- Customize models for individual stores  
- Build a dashboard using Power BI or Streamlit  

---

## 11. Conclusion
The SARIMAX model provided robust sales forecasts, enabling Walmart to optimize inventory planning. The model identified key drivers such as unemployment and holidays, aiding strategic business planning.

---

## 12. References
- [Walmart Sales Dataset (Kaggle/Provided)]  
- [Statsmodels SARIMAX Documentation](https://www.statsmodels.org/stable/generated/statsmodels.tsa.statespace.sarimax.SARIMAX.html)  
- [Joblib Docs](https://joblib.readthedocs.io/en/latest/)  
- [Seaborn](https://seaborn.pydata.org/)  
- [Matplotlib](https://matplotlib.org/)  
- McKinney, W. (2017). *Python for Data Analysis*. O'Reilly.  
- OpenAI. [ChatGPT Documentation](https://www.openai.com)

---
