# Machine Learning-Based Demand Forecasting and Inventory Planning for a Computer Retail Shop
---

## Team Members

| Member | Name | Student ID | Role |
|--------|------|------------|------|
| Member 1 | Methpani M.M.K | IT24100301 | Data Collection & EDA Lead |
| Member 2 | Henarangoda M.P | IT24100889 | Data Preprocessing & Feature Engineering Lead |
| Member 3 | Sandeepa H.M.D.P | IT24101554 | Model Training & Development Lead |
| Member 4 | Jayasekara D.T.B | IT24100476 | Model Evaluation & Business Recommendation Lead |

---

## Project Overview

### Business Scenario
A computer retail shop sells a range of product categories, brands and capacities, such as laptops, RAM and SSDs. To keep suitable stock levels, the shop needs a reliable estimate of future product demand.

### Problem Statement
Inaccurate demand estimation can lead to stock shortages or excess inventory. This project predicts the quantity of a selected product segment that is expected to be sold during the **following month**.

### Project Goal
Develop a machine learning system that forecasts next-month product demand and supports inventory-planning decisions.

---

## Business Lens

- **Primary lens – Demand Forecasting:** Predict the expected sales quantity of a selected product segment for the next month, helping the shop identify sales patterns and prepare suitable inventory levels.
- **Secondary lens – Inventory Planning:** Use the forecast to decide how much stock to prepare, reducing the risk of shortages and unnecessary excess inventory.

---

## Machine Learning Task

| Item | Description |
|------|-------------|
| **Task** | Supervised regression – next-month product demand forecasting |
| **Target variable** | `next_month_quantity` (units expected to be sold next month) |
| **Unit of analysis** | A product segment for a particular month, defined by stable attributes: product category, brand, capacity and relevant specifications |
| **Why segments?** | Individual computer models may be discontinued or replaced, so the project does not focus on single models |

### Expected Model Output
- Selected product segment
- Predicted next-month sales quantity
- Historical demand information
- Forecasting results
- Inventory-planning insights

### Evaluation Metrics
- **MAE** (Mean Absolute Error) – emphasised, as it shows the average prediction error in units
- **RMSE** (Root Mean Squared Error)
- **R² Score**

---

## Proposed Workflow

1. **Problem Understanding** – Define the shop's demand-planning problem and the forecasting objective.
2. **Data Understanding & Quality Assessment** – Study the dataset, data dictionary, data types, missing values, duplicates and inconsistent records.
3. **Exploratory Data Analysis** – Analyse demand by category, brand, capacity and time period.
4. **Data Preprocessing** – Clean data, handle missing values and outliers, fix inconsistencies and prepare data for modelling.
5. **Feature Engineering** – Create leakage-free features such as previous month's sales, previous-month demand averages, historical sales trends, category, brand, capacity and month/seasonal information.
6. **Model Development** – Train Linear Regression, Decision Tree Regressor, Random Forest Regressor and XGBoost Regressor, plus a simple baseline (historical average or previous-month demand).
7. **Model Comparison** – Compare models on accuracy, complexity, interpretability and business suitability.
8. **Evaluation & Validation** – Use chronological train-test splitting or time-aware validation so earlier data predicts later periods.
9. **Business Recommendation** – Convert the forecast into an inventory-planning insight.

> **Example:** Predicted next-month demand for Kingston 16GB RAM: **37 units**. This helps the inventory manager plan the required stock.

The full workflow diagram is included in the project report (Figure 1).

---

## Models

| Model | Purpose |
|-------|---------|
| Baseline (historical average / previous month) | Reference point for comparison |
| Linear Regression | Simple, interpretable model |
| Decision Tree Regressor | Non-linear, rule-based model |
| Random Forest Regressor | Ensemble of trees for robust predictions |
| XGBoost Regressor | Gradient boosting for high accuracy |

All models are trained and tuned by **Member 3 (Sandeepa H.M.D.P)**.

---

## Member Responsibilities

### Member 1 – Methpani M.M.K (IT24100301)
**Role:** Data Collection & Exploratory Data Analysis Lead

- Collect the dataset and prepare the dataset description and data dictionary
- Perform the data-quality assessment (missing values, duplicates, inconsistent records) and write the data-quality report
- Carry out Exploratory Data Analysis to identify product-demand patterns across categories, brands, capacities and time periods
- Prepare and maintain the **EDA Insight Log**
- Support the product-segment definition with insights from the analysis

### Member 2 – Henarangoda M.P (IT24100889)
**Role:** Data Preprocessing & Feature Engineering Lead

- Clean the data, handle missing values and investigate outliers
- Correct inconsistent records and perform categorical encoding
- Build the product-segment dataset and construct the target `next_month_quantity`
- Engineer features (lag features, rolling averages, trends, seasonal features) without using future information
- Prepare the chronological train/validation/test split
- Maintain the **Preprocessing & Feature Engineering Log**

### Member 3 – Sandeepa H.M.D.P (IT24101554)
**Role:** Model Training & Development Lead

*Member 3 is the only member responsible for model training.*

- Build the forecasting baseline (historical average / previous-month demand)
- Train all four regression models: **Linear Regression, Decision Tree, Random Forest and XGBoost**
- Perform hyperparameter tuning and time-aware cross-validation where appropriate
- Analyse the relationship between product features and demand (e.g. feature importance)
- Generate the final next-month demand forecasts and hand model predictions over to Member 4 for evaluation

### Member 4 – Jayasekara D.T.B (IT24100476)
**Role:** Model Evaluation & Business Recommendation Lead

- Evaluate the trained models using MAE, RMSE and R²
- Compare models on accuracy, complexity, interpretability and business suitability
- Perform error analysis and time-aware validation checks
- Convert final forecasts into practical **inventory-planning recommendations**
- Document the project's limitations and responsible-AI considerations

---

## Expected Deliverables

1. Business problem definition
2. Dataset description and data dictionary
3. Data-quality report
4. EDA and EDA Insight Log
5. Preprocessing and Feature Engineering Log
6. Product-segment definition
7. Target-construction method
8. Forecasting baseline
9. Four trained regression models
10. Model comparison report
11. Time-aware validation results
12. Final next-month demand forecasts
13. Inventory-planning recommendations
14. Decision Log
15. Limitations and responsible AI considerations
16. Source code and project documentation

---

## Challenges and Responsible Use

The project considers challenges such as changing product models, limited historical data, unexpected demand fluctuations, seasonal patterns, supplier-related issues and newly introduced products. Performance, assumptions, limitations and business implications are documented so forecasts are interpreted responsibly.

This system is a **decision-support tool** for the shop owner or inventory manager. It does not replace human judgement.

---

## Conclusion

This project aims to deliver a reproducible, evidence-based and practically useful demand forecasting solution that connects machine learning techniques with a real-world inventory-planning problem, helping the shop reduce stock shortages and minimise excess inventory.
