# Data Analysis

## Summary of Scripts & Notebooks

---

## [`01_data_quality_prep.ipynb`](../4_data_analysis/pm25_health_impact_analysis/01_data_quality_prep.ipynb) — *Data Cleaning & Feature Engineering*

**Objective:**  
Prepares the foundational dataset (`analysis_ready_data.csv`) for all subsequent
analysis.

**Key Steps:**

- Loads the raw dataset (`clean_merged_data.csv`) and inspects structure and contents.
- Engineers new features:
  - **Lag features**: `PM25_lag1`, `PM25_lag2`
  - **Rolling averages**: `PM25_3yr_avg`, `PM25_5yr_avg`
  - **Interaction term**: `PM2.5 × SDI`
  - **SDI category**: for stratified analysis
- Exports cleaned and enriched dataset as `analysis_ready_data.csv`

---

## [`02_exploratory_trends.ipynb`](../4_data_analysis/pm25_health_impact_analysis/02_exploratory_trends.ipynb) — *Exploratory Data Analysis (EDA)*

**Objective:**  
Visualizes patterns, trends, and correlations in the prepared dataset.

**Key Steps:**

- **Descriptive statistics** and **histograms** to explore distributions
- **Temporal trends** of PM₂.₅ and DALYs (2010–2019), stratified by SDI
- **Country-level comparisons**: bar plots of top/bottom PM₂.₅ countries,
scatterplots of PM₂.₅ vs. DALYs
- **Choropleth map** of global average PM₂.₅ using Plotly
- **Correlation matrix** using heatmap
- Exports summary metrics (`country_avg.csv`) for each country

---

## [`03_modeling_dalys.ipynb`](../4_data_analysis/pm25_health_impact_analysis/03_modeling_dalys.ipynb) — *Predictive Modeling of DALYs*

**Objective:**  
Trains regression models to predict DALYs using PM₂.₅ and socio-demographic features.

**Key Steps:**

- Loads data and selects predictors/targets
- Trains models for four DALY outcomes:
  - **Linear Regression**
  - **Random Forest** (saved as `.pkl`)
- Evaluates model performance using **R²** and **RMSE**
- Exports model performance table to CSV
- **Diagnostic plots**:
  - Predictions vs. Actual
  - Residuals vs. Predicted

---

## [`04_sdi_vulnerability.ipynb`](../4_data_analysis/pm25_health_impact_analysis/04_sdi_vulnerability.ipynb) — *Vulnerability & Threshold Analysis by SDI*

**Objective:**  
Assesses how PM₂.₅-related health outcomes vary across SDI levels.

**Key Steps:**

- Loads `analysis_ready_data.csv` and `country_level_averages.csv`
- **Vulnerability modeling**: trains Random Forests for each SDI group
- Visualizes:
  - **Model performance (R²)** by SDI
  - **Feature importance** (current, lagged, and average PM₂.₅)
- **Threshold analysis**: Compares DALYs above vs. below global median PM₂.₅ for
each SDI group
- **Sensitivity analysis**: Tests robustness using alternative feature sets

---

## [`covid_analysis_mlr.ipynb`](../4_data_analysis/pm25_covid_mortality/covid_analysis_mlr.ipynb) — *COVID-19 Mortality: Linear Models*

**Objective:**  
Examines the relationship between PM₂.₅, SDI, and COVID-19 mortality using
multiple linear regression.

**Model Summary:**

| Model Type             | PM₂.₅ | SDI  | Interaction| R²  | Fit  | Assumptions Met|
|-------------------------|--------|------|-------------|------|--------|------------------|
| Linear Regression       | ✅     | ✅   | N/A         | 0.29 | Moderate| Partial|
| Log-Transformed         | Modest | Modest | N/A       | 0.19 | Modest  | Partial|
| Interaction Model       | ❌     | ❌   | ❌          | 0.19 | Modest | Partial|

**Key Takeaways:**

- PM₂.₅ and SDI are modest but statistically significant predictors.
- No significant PM₂.₅ × SDI interaction was found.
- Linear models explained only a modest portion of variance (max R² = 0.29).
- Diagnostic plots revealed some violations (outliers, heteroscedasticity).
- Models tended to overpredict low-mortality and underpredict high-mortality countries.

---

## [`covid_mortality_advanced_modeling.ipynb`](../4_data_analysis/pm25_covid_mortality/covid_mortality_advanced_modeling.ipynb) — *Machine Learning & Nonlinear Models*

**Objective:**  
Applies advanced modeling techniques to better understand PM₂.₅–mortality relationships.

**Key Insights:**

- **Random Forest:** Explained 24% of variance; SDI (55%) slightly more
important than PM₂.₅ (45%).
- **Spline Regression:** Explained 35%; nonlinear PM₂.₅ effect, SDI protective.
- **Spline Interaction Model:** Explained 40%; interaction terms significant.
- **Quantile Regression:** PM₂.₅ effect stronger at low mortality levels; SDI
protective across all quantiles.
- **Influential Countries:** Somalia, Eswatini, Bahamas, Afghanistan, and CAR had
disproportionate leverage—warranting sensitivity checks.
