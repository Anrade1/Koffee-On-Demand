# Koffee-On-Demand
Time-series demand forecasting and exploratory analysis of coffee vending machine transaction data, including seasonal pattern analysis and baseline machine learning modeling.
# Coffee Vending Machine Demand Forecasting

## Project Overview

This project analyzes transaction-level coffee vending machine sales data to uncover purchasing patterns and build a baseline demand forecasting model. The goal is to translate daily transaction data into actionable insights that improve inventory planning, product assortment, and revenue optimization.

Module 20 focuses on exploratory data analysis (EDA) and baseline model development to establish a foundation for advanced time-series forecasting in Module 24.

---

## Research Question

**What sales trends and customer purchasing patterns emerge from daily coffee vending machine transactions, and how can these insights be used to forecast demand and optimize product offerings?**

---

## Dataset Overview

The dataset contains **3,547 transaction-level records** spanning **381 days** (March 2024 – early 2025).

Each record includes:

- Date
- Time of transaction
- Hour of day
- Product type (coffee variety)
- Payment method
- Revenue per transaction

For forecasting purposes, transactions were aggregated to the **daily level**.

---

## Exploratory Data Analysis (EDA)

### 1. Revenue Trends

- Daily revenue exhibits high volatility.
- A 7-day rolling average confirms strong weekly seasonality.
- A mild upward shift in revenue appears in early 2025.

### 2. Weekly Seasonality

- Weekdays significantly outperform weekends.
- Tuesday is the highest-performing day.
- Sunday is the lowest-performing day.
- Revenue varies by approximately 25–30% between peak and trough days.

### 3. Hourly Demand Patterns

- Peak transaction volume occurs between **9–11 AM**, with 10 AM highest.
- Demand declines steadily after 7 PM.
- Patterns suggest commuter-driven purchasing behavior.

### 4. Product Preference by Time of Day

**Morning (8–11 AM):**
- Americano with Milk dominates.
- Strong, simpler coffee options preferred.

**Afternoon (12–5 PM):**
- Latte becomes the top product.
- Increased demand for milk-based beverages.
- Hot chocolate appears more frequently.

This indicates clear time-of-day behavioral segmentation.

---

## Feature Engineering

To support forecasting, the following features were created:

- Day of week
- Month
- Weekend indicator
- Lag 1 (previous day revenue)
- Lag 7 (revenue 7 days prior)
- Rolling 7-day average revenue

These features capture seasonality and short-term demand persistence.

---

## Baseline Model (Module 20)

**Model:** RandomForestRegressor  
**Target:** Daily Revenue  
**Train/Test Split:** Chronological (80/20)

### Performance Metrics

- **MAE:** 127.25  
- **RMSE:** 157.17  
- **R²:** 0.326  

The model captures structural demand patterns but struggles with extreme daily volatility.

---

## Feature Importance

The model relies primarily on:

1. Rolling 7-day average (strongest predictor)
2. Lag 1 and Lag 7 features
3. Calendar features (day of week, month)

This indicates strong autoregressive structure and persistent weekly demand cycles.

---

## Business Implications

The analysis reveals:

- Clear weekday-driven demand
- Morning commuter peak behavior
- Time-based product segmentation
- Predictable weekly seasonality

Operational improvements could include:

- Morning-focused inventory planning
- Weekend inventory adjustment
- Product assortment alignment with time-of-day behavior
- Data-driven demand forecasting rather than intuition

---

## Next Steps (Module 24)

- Implement SARIMA for explicit seasonal modeling
- Compare classical time-series forecasting vs machine learning
- Expand lag structure
- Apply time-series cross-validation
- Improve forecasting stability

---

## Conclusion

This project establishes a structured baseline for demand forecasting in a micro-retail environment. The results demonstrate that daily revenue patterns exhibit strong weekly seasonality and short-term persistence, making time-series modeling an appropriate next step.
