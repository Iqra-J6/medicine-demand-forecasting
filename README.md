# 💊 Medicine Demand Forecasting & Pharmacy Inventory Optimisation

An end-to-end **Data Science and Machine Learning project** exploring how historical medicine demand and hospital activity can be used to forecast future demand, identify inventory risks, and support pharmacy stock-planning decisions.

This project was originally developed as part of the **Amdari 1-Week Virtual Data Science Work Experience**, using the simulated **Northbridge Healthcare** case study. I subsequently extended the original project independently with additional model benchmarking, financial risk analysis, explainability, scenario modelling, and decision-support functionality.

> **Note:** Northbridge Healthcare is a simulated project scenario. This project does not use real NHS patient data and should not be interpreted as a deployed NHS system.

---

## 🎯 Business Problem

Pharmacy inventory management requires balancing two competing risks:

- **Understocking** can result in medicine shortages, treatment delays, and costly emergency orders.
- **Overstocking** can increase storage costs, tie up resources, and contribute to medicine wastage or expiry.

The central question explored in this project is:

> **How much medicine should be ordered for the next month based on historical demand and hospital activity?**

The objective was therefore not simply to build a machine-learning model, but to translate forecasting results into useful inventory decisions.

---

## 📊 Project Workflow

The project follows an end-to-end data science workflow:

**Business Understanding → Data Preparation → Exploratory Data Analysis → Feature Engineering → Forecasting → Model Evaluation → Inventory Risk Analysis → Decision Support**

### 1. Data Preparation & EDA

I explored and prepared multiple datasets covering:

- Medicine dispensing demand
- Medicine information
- Hospital information
- Hospital activity
- Current inventory levels
- Emergency orders
- Medicine wastage

The analysis included missing-value checks, duplicate detection, data-type validation, merging datasets, trend analysis and investigation of operational patterns.

---

## 🧠 Feature Engineering

Time-series and operational features were created to help capture patterns in medicine demand, including:

- Historical demand lags
- Rolling demand information
- Month and year information
- Seasonal patterns
- Hospital activity variables
- Current stock information

These features allowed both traditional statistical forecasting and machine-learning approaches to be explored.

---

## 🤖 Forecasting Models

### SARIMAX

A **SARIMAX** model was used to capture temporal patterns and seasonality in medicine demand.

This provides a statistical forecasting approach that is particularly useful when historical demand follows recurring patterns.

### XGBoost

An **XGBoost regression model** was also developed using engineered features.

XGBoost provides a machine-learning alternative capable of modelling more complex and non-linear relationships between historical demand, time-based features and operational variables.

---

## 📏 Model Evaluation

Forecasting performance was assessed using metrics including:

- **MAE — Mean Absolute Error**
- **RMSE — Root Mean Squared Error**
- **MAPE — Mean Absolute Percentage Error**

I also independently added a **seasonal-naïve baseline model**.

This allowed the more complex SARIMAX and XGBoost models to be compared against a simple assumption:

> Next month's demand will resemble demand from the corresponding historical seasonal period.

This is important because additional model complexity should only be justified when it provides meaningful forecasting improvement.

---

# 🚀 Independent Portfolio Extensions

After completing the original internship requirements, I continued developing the project independently.

The following sections were added beyond the original project scope.

## 💊 Medicine Inventory Risk Prioritisation

I developed an additional risk-analysis layer that translates forecasts into operational inventory signals.

Medicines can be classified into categories such as:

- 🔴 Critical Shortage Risk
- 🟠 Shortage Risk
- 🟢 Healthy / Monitor
- 🟡 Excess Stock Risk

A priority score is then used to identify medicines that may require attention first.

This moves the project from simply asking:

**"What will demand be?"**

towards:

**"Given predicted demand and available stock, where should the pharmacy team focus its attention?"**

---

## 💷 Financial Inventory Exposure

I extended the inventory analysis by combining predicted inventory gaps with medicine unit costs.

This provides indicative estimates for:

- Potential shortage exposure
- Excess inventory value
- Total inventory value potentially at risk

This helps translate technical forecasting outputs into a metric that business and operational stakeholders can more easily interpret.

These values represent **inventory-value estimates rather than verified financial savings or losses**.

---

## 🔍
