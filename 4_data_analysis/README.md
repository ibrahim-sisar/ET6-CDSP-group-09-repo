<h1 style="display: flex; align-items: center;">
  Data Analysis
  <img src="../notes/images/data_analysis.gif" alt="data" style="height:50px; margin-left:10px;">
</h1>

In this folder, we seek to answer the following question:

> **To what extent have ambient PM₂.₅ concentrations (2010–2019)
influenced the burden of cardiovascular and respiratory diseases across
countries with varying socio-demographic development levels, and how might
this long-term exposure relate to COVID-19 mortality outcomes in 2020?**

To investigate this, the `4_data_analysis` folder brings together all the
notebooks and supporting files used in our statistical and machine
learning analysis of global health outcomes related to air pollution
and socio-demographic conditions.

---

## Objectives

1. **Objective 1:** Examine the relationship between
ambient PM₂.₅ (2010–2019) and the burden of all-causes, cardiovascular, Stroke,
and respiratory diseases measured using
Disability-Adjusted Life
Years (DALY)rates across countries with varying levels of socio-demographic
development (SDI).

2. **Objective 2:** Investigate whether long-term exposure to PM₂.₅
is associated with differences in COVID-19 mortality rates across countries
in 2020, and explore how this relationship may interact with national
development levels.

---

## Summary of Scripts & Notebooks

## [`01_data_quality_prep.ipynb`][1] — *Data Cleaning & Feature Engineering*

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

## [`02_exploratory_trends.ipynb`][2] — *Exploratory Data Analysis (EDA)*

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

## [`03_modeling_dalys.ipynb`][3] — *Predictive Modeling of DALYs*

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

## [`04_sdi_vulnerability.ipynb`][4] — *Vulnerability & Threshold Analysis by SDI*

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

## [`covid_analysis_mlr.ipynb`][5] — *COVID-19 Mortality: Linear Models*

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

## [`covid_mortality_advanced_modeling.ipynb`][6] —*Machine Learning Models*

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

---

## Technical Documentation

Detailed methodology, results interpretation, and model diagnostics are provided
in the following files:

- [`pm25_health_technical_explanation.md`](pm25_health_technical_explanation.md)
– Full documentation for **Objective 1**
- [`covid_mortality_technical_explanation.md`](covid_mortality_technical_explanation.md)
– Full documentation for **Objective 2**

<!-- Notebook reference links (hidden from view) -->
[1]: ../4_data_analysis/pm25_health_impact_analysis/01_data_quality_prep.ipynb
[2]:../4_data_analysis/pm25_health_impact_analysis/02_exploratory_trends.ipynb
[3]:../4_data_analysis/pm25_health_impact_analysis/03_modeling_dalys.ipynb
[4]:../4_data_analysis/pm25_health_impact_analysis/04_sdi_vulnerability.ipynb
[5]:../4_data_analysis/pm25_covid_mortality/covid_analysis_mlr.ipynb
[6]:../4_data_analysis/pm25_covid_mortality/covid_mortality_advanced_modeling.ipynb
