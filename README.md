# Cement Demand Forecasting and Inventory Simulation Across Multiple Construction Sites

## Project Overview

This project was developed for Midlands Infrastructure Group (MIG) to forecast cement demand across multiple construction sites and support inventory planning through predictive analytics.

The solution combines machine learning forecasting, inventory simulation, site-level risk analysis, and dashboard reporting to help project managers make proactive operational decisions.

The project addresses common construction supply chain challenges such as:

* Cement stock shortages
* Overstocking and excess inventory
* Emergency deliveries
* Material waste
* Poor inventory visibility
* Demand planning inefficiencies

---

# Business Problem

Construction projects require accurate cement demand forecasts to ensure materials are available when needed.

Traditional forecasting methods often rely on manual estimates, which can result in:

* Stockouts
* Delayed construction activities
* Excess inventory carrying costs
* Unplanned procurement expenses
* Poor inventory utilization

The goal of this project was to develop a data-driven forecasting solution capable of predicting cement consumption and supporting inventory optimization across multiple construction sites.

---

# Project Objectives

The project aimed to:

* Forecast cement demand across construction sites
* Identify key factors influencing cement consumption
* Compare forecasting models
* Simulate future inventory levels
* Detect inventory shortage risks
* Support proactive replenishment planning
* Develop an operational dashboard for business users

---

# Dataset Overview

The dataset contains:

* 32,880 records
* 30 construction sites
* 3 cement types

### Key Variables

* Date
* Site ID
* Cement Type
* Planned Pour Tonnes
* Consumed Tonnes
* Opening Inventory
* Deliveries
* Closing Inventory
* Rainfall
* Temperature
* Silo Capacity

---

# Project Methodology

The project followed the following workflow:

### 1. Data Extraction

Data was loaded from a SQLite database.

### 2. Data Cleaning

The dataset was validated for:

* Missing values
* Duplicate records
* Data consistency
* Outliers

### 3. Exploratory Data Analysis (EDA)

EDA was performed to understand:

* Consumption patterns
* Site-level demand behavior
* Weather impacts
* Inventory trends

### 4. Feature Engineering

Additional variables were created to improve forecasting performance, including:

* Month
* Day of week
* Lagged operational variables

### 5. Model Development

Two forecasting approaches were evaluated:

* Random Forest Regressor
* SARIMAX Time Series Model

### 6. Model Evaluation

Models were compared using:

* MAE (Mean Absolute Error)
* RMSE (Root Mean Squared Error)
* R² Score

### 7. Inventory Simulation

Forecast outputs were integrated into an inventory simulation model to estimate future inventory levels and identify potential inventory risks.

### 8. Dashboard Development

Power BI dashboards were developed to visualize:

* Forecast performance
* Feature importance
* Inventory risks
* Site-level inventory projections

---

# Model Performance Results

| Model         | MAE  | RMSE | R² Score |
| ------------- | ---- | ---- | -------- |
| Random Forest | 0.16 | 0.71 | 0.998    |
| SARIMAX       | 7.28 | 9.94 | 0.65     |

### Best Performing Model

Random Forest significantly outperformed SARIMAX across all evaluation metrics and was selected as the final forecasting model.

---

# Key Findings

### Forecast Accuracy

The Random Forest model achieved highly accurate demand forecasts with:

* RMSE: 0.71
* MAE: 0.16
* R² Score: 0.998

### Key Demand Drivers

Feature importance analysis revealed that the strongest drivers of cement demand were:

1. Planned Pour Tonnes
2. Rainfall
3. Deliveries
4. Opening Inventory
5. Average Temperature

### Inventory Insights

Inventory simulation revealed:

* Sites with low projected inventory requiring monitoring
* Sites maintaining healthy inventory levels
* Opportunities for proactive replenishment planning

---

# Inventory Simulation Logic

The inventory simulation estimated future inventory levels using forecasted cement demand.

### Formula

Projected Closing Inventory = Opening Inventory + Deliveries − Forecasted Consumption

### Example

Assume a site starts with:

* Opening Inventory = 5,000 tonnes

Additional deliveries received:

* Deliveries = 2,000 tonnes

Forecasted consumption:

* Forecasted Consumption = 6,000 tonnes

Projected inventory becomes:

5,000 + 2,000 − 6,000 = 1,000 tonnes

This indicates that the site may face inventory risk if future demand increases unexpectedly.

The simulation was applied across all construction sites.

---

# Dashboard Visualizations

The Power BI dashboard includes the following business-focused visualizations.

## Actual vs Predicted Cement Consumption

Compares forecasted cement demand against actual consumption values.

Business Value:

* Validates forecasting accuracy
* Builds confidence in model predictions

---

## Feature Importance Analysis

Identifies the variables that most influence cement demand.

Business Value:

* Helps planners understand demand drivers
* Supports operational decision-making

---

## Top 15 Forecast Error by Site

Highlights sites with the largest forecasting deviations.

Interpretation:

* Positive values indicate actual demand exceeded forecasted demand.
* Negative values indicate forecasted demand exceeded actual demand.

Business Value:

* Identifies locations requiring forecast monitoring
* Supports continuous model improvement

---

## Top 10 Inventory Risk Sites

Identifies sites projected to have the lowest remaining inventory after forecasted consumption.

Business Value:

* Supports replenishment planning
* Reduces stockout risk

---

## Top 10 Projected Closing Inventory Sites

Shows sites expected to maintain the highest inventory levels.

Business Value:

* Identifies excess inventory concentrations
* Supports inventory balancing decisions

---

## Opening vs Projected Closing Inventory

Compares inventory before and after forecasted consumption.

Business Value:

* Measures inventory utilization
* Supports inventory planning and optimization

---

# Exported Deliverables

The project generated the following outputs:

### Forecast Outputs

* forecast_results.csv
* forecast_results_site_level.csv

### Inventory Simulation Outputs

* inventory_simulation.csv
* inventory_simulation_site_level.csv

### Model Evaluation Outputs

* model_comparison.csv
* feature_importance.csv

### Visualizations

* actual_vs_predicted.png
* feature_importance.png
* forecast_error_by_site.png
* top15_forecast_error_by_site.png
* top10_inventory_risk_sites.png
* top10_projected_closing_inventory_by_site.png
* opening_vs_closing_inventory_by_site.png

### Dashboard

* Power BI Forecast Dashboard
* Site-Level Inventory Dashboard

---

# Business Impact

This solution provides value by:

* Improving demand visibility
* Supporting inventory planning
* Reducing stockout risk
* Improving delivery scheduling
* Enhancing inventory utilization
* Supporting data-driven operational decisions

---

# Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Scikit-Learn
* Statsmodels
* SQLite
* Jupyter Notebook
* Power BI
* Git
* GitHub

---

# Future Improvements

Potential future enhancements include:

* Real-time forecasting dashboards
* Automated inventory alerts
* API deployment for forecasting services
* Integration with live construction data
* Advanced machine learning models such as XGBoost and LSTM
* Enterprise inventory optimization solutions

---

# Conclusion

The project successfully developed a machine learning-based cement demand forecasting and inventory simulation solution for Midlands Infrastructure Group.

The Random Forest model achieved excellent forecasting performance and provided the foundation for site-level inventory simulation and operational risk analysis.

The final solution demonstrates how predictive analytics can improve construction inventory management, support proactive planning, and enable more informed business decisions across multiple construction sites.
