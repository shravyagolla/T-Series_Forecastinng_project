# T-Series Forecasting Project

## Project Overview

This project is a Databricks-based **Predictive Maintenance and Machine Failure Analytics** solution designed to analyze industrial machine data using **PySpark, Delta Lake, Machine Learning, and Deep Learning**.

The project processes machine telemetry, error events, component failures, machine information, and maintenance records through a **Medallion Architecture** and generates predictive insights related to machine health, anomalies, failure risk, component failures, Remaining Useful Life, maintenance effectiveness, and MTBF.

## Objectives

* Analyze error patterns before component failures
* Understand machine age, model, and baseline sensor behavior
* Analyze the impact of maintenance on sensor stability
* Forecast voltage and vibration 12 hours ahead
* Detect multi-sensor anomalies without standard error codes
* Predict machine failure risk within the next 24 hours
* Predict the next component likely to fail
* Estimate Remaining Useful Life (RUL)
* Evaluate preventive maintenance effectiveness
* Analyze MTBF across machine models and components

## Architecture

```text
Raw CSV Data
     |
     v
Bronze Layer
     |
     v
Silver Layer
     |
     v
Gold Layer
     |
     v
Machine Learning & Analytics
     |
     v
Business Insights & Visualizations
```

## Medallion Architecture

### Bronze Layer

Loads the raw predictive-maintenance datasets into Databricks Delta tables.

### Silver Layer

Cleans and prepares the data by handling duplicates, null values, timestamps, and data types. Creates analysis-ready Silver tables.

### Gold Layer

Creates business-level analytical and machine-learning tables. Performs aggregations, joins, feature engineering, predictions, and visualizations for each business question.

## Project Notebooks

| Notebook      | Analysis                         |
| ------------- | -------------------------------- |
| `01_Bronze`   | Raw data ingestion               |
| `02_Silver`   | Data cleaning and transformation |
| `03_Gold_Q1`  | Error and failure analysis       |
| `04_Gold_Q2`  | Machine baseline analysis        |
| `05_Gold_Q3`  | Maintenance stability analysis   |
| `06_Gold_Q4`  | 12-hour telemetry forecasting    |
| `07_Gold_Q5`  | Multi-sensor anomaly detection   |
| `08_Gold_Q6`  | 24-hour failure-risk prediction  |
| `09_Gold_Q7`  | Component failure prediction     |
| `10_Gold_Q8`  | Remaining Useful Life prediction |
| `11_Gold_Q9`  | Maintenance effectiveness        |
| `12_Gold_Q10` | MTBF analysis                    |

## Key Model Performance

| Use Case                   | Model                    | Result                       |
| -------------------------- | ------------------------ | ---------------------------- |
| Q4 — Telemetry Forecasting | LSTM                     | Test MSE: **0.0081**         |
| Q5 — Anomaly Detection     | Isolation Forest         | **8,761 anomalies detected** |
| Q6 — Failure Risk          | Logistic Regression      | ROC-AUC: **77.21%**          |
| Q7 — Component Prediction  | Random Forest            | Accuracy: **94.12%**         |
| Q8 — RUL Prediction        | Random Forest Regression | MAE: **43.11 days**          |

## Results Summary

* **876,100** telemetry records analyzed.
* **8,761** multi-sensor anomalies detected.
* **8,703** detected anomalies had no associated error code.
* LSTM generated **12-hour voltage and vibration forecasts**.
* Random Forest achieved **94.12% accuracy** for component failure prediction.
* Logistic Regression achieved **77.21% ROC-AUC** for 24-hour failure-risk prediction.
* RUL prediction achieved **43.11 days MAE**.
* MTBF analysis compared machine models and components to support maintenance planning.

## Key Gold Tables

* `gold_q1_error_failure`
* `gold_q2_machine_baseline`
* `gold_q2_model_baseline`
* `gold_q3_maintenance_stability`
* `gold_q4_telemetry_forecast`
* `gold_q5_multisensor_anomaly`
* `gold_q6_failure_risk`
* `gold_q7_component_prediction`
* `gold_q8_rul_prediction`
* `gold_q9_maintenance_effectiveness`
* `gold_q10_mtbf`

## Key Analysis Areas

### Error and Failure Analysis

Analyzes:

* Error frequency
* Component failures
* Error patterns before failures
* 24–48 hour failure windows

### Machine Baseline Analysis

Analyzes:

* Machine age
* Machine model
* Voltage
* Rotation
* Pressure
* Vibration

### Maintenance Stability

Analyzes:

* Days since maintenance
* Sensor variability
* Voltage stability
* Pressure variability
* Vibration variability

### Telemetry Forecasting

Uses an **LSTM model** to forecast:

* Voltage
* Vibration
* 12-hour future sensor behavior

### Anomaly Detection

Uses **Isolation Forest** to identify:

* Multi-sensor anomalies
* Unusual machine states
* Anomalies without standard error codes

### Failure Risk

Uses **Logistic Regression** with 7-day rolling sensor features to estimate:

* 24-hour failure probability
* Machine-level failure risk

### Component Failure Prediction

Uses **Random Forest Classification** to predict:

* `comp1`
* `comp2`
* `comp3`
* `comp4`

### Remaining Useful Life

Uses **Random Forest Regression** to estimate:

* Days remaining before component failure
* Component-level RUL after maintenance

### Maintenance Effectiveness

Analyzes:

* Maintenance events
* Failures after maintenance
* Time between maintenance and failure

### MTBF Analysis

Analyzes:

* Machine model
* Component
* Maintenance events
* Time to next failure
* Mean Time Between Failures

## Data Visualization

Databricks visualizations are used to present:

* Error and failure relationships
* Machine age and sensor behavior
* Maintenance stability
* Telemetry forecasts
* Multi-sensor anomalies
* Failure-risk rankings
* Component failure predictions
* RUL predictions
* Maintenance outcomes
* MTBF by machine model and component

## Technologies Used

* Databricks
* PySpark
* Python
* Delta Lake
* Scikit-learn
* TensorFlow
* LSTM
* Random Forest
* Logistic Regression
* Isolation Forest
* Databricks Notebooks
* GitHub
* Medallion Architecture

## Project Outcome

The project demonstrates how **Databricks and PySpark** can be used to build an end-to-end predictive-maintenance pipeline using the Medallion Architecture.

The final Gold layer provides business-ready datasets and machine-learning outputs for **anomaly detection, sensor forecasting, failure-risk prediction, component failure prediction, RUL estimation, maintenance effectiveness, and MTBF analysis**.

### Author

**Shravya**
