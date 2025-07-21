# Technical Description of PM₂.₅ Health Impact Analysis

## 1. Introduction

This study evaluates the association between ambient fine particulate matter
(PM₂.₅) concentrations (2010–2019) and population health burdens—quantified by
Disability-Adjusted Life Years (DALYs)—across countries. We also examine how
socio-demographic development, measured by the Socio-Demographic Index (SDI),
modifies pollution-related health outcomes.

## 2. Data and Preprocessing

- **Sources**: Country-level annual PM₂.₅ (2010–2019), DALYs for all-cause,
  cardiovascular, stroke, and respiratory diseases, and SDI values.
- **Harmonization**: Standardized country names, synchronized on
  `(country, year)`, and dropped nations with >20% missing values.
- **Quality Checks**: Inspected distributions and missingness patterns; imputed
  occasional gaps via linear interpolation.

## 3. Feature Engineering

- **Lagged Exposure**: Generated 1-year and 2-year lagged PM₂.₅ to capture
  delayed health effects.
- **Rolling Averages**: Computed 3- and 5-year moving averages (e.g.,
  `PM25_5yr_avg`) to smooth short-term fluctuations.
- **SDI Stratification**: Employed SDI continuously and defined low/medium/high/
  very-high strata for subgroup modeling.

## 4. Modeling Approaches

### 4.1 Linear Regression (Baseline)

- **Purpose**: Provide interpretable, average marginal effects of PM₂.₅ and SDI
  on DALYs.

### 4.2 Random Forest Regression

- **Purpose**: Capture non-linearities and high-order interactions without
  explicit specification.
- **Tuning**: Optimized number of trees (100–500), tree depth (5–15), and
  minimum samples per leaf (5–20) via grid search and 5-fold cross-validation.

## 5. Model Evaluation & Key Findings
<!-- markdownlint-disable MD013 -->

| Outcome              | R²   | Top Predictor     | Secondary Predictor | Corr(PM₂.₅, DALY)   |
|----------------------|------|-------------------|--------------------|------|
| All-cause DALYs      | 0.789| SDI (24.7%)       | PM₂.₅               | 0.58  |
| Cardiovascular DALYs | 0.793| SDI (21.7%)       | PM25_5yr_avg         | 0.53 |
| Stroke DALYs         | 0.734| SDI (23.2%)       | PM25_5yr_avg         | 0.59 |
| Respiratory DALYs    | 0.652| SDI (22.5%)       | PM₂.₅               | 0.55  |
<!-- markdownlint-disable MD013 -->

> **Note**: The `Corr` column shows the Pearson correlation
> between annual PM₂.₅ concentrations and DALY rates for all causes.

- **Interpretation**: Random Forest consistently outperforms Linear Regression
  (baseline R² ~0.45), revealing complex, non-linear pollutant-health
  relationships. SDI emerges as the dominant driver in all models, followed by
  current or lagged PM₂.₅.

## 6. Development & Pollution Trends

- **SDI Effect**: Higher-SDI countries display substantially lower DALY burdens
  and steeper declines over 2010–2019.
- **PM₂.₅ Effects**: Positive, moderate correlations across outcomes; lagged and
  moving-average exposures matter more for cardiovascular and stroke DALYs.
- **Subgroup Vulnerability**: Low- and medium-SDI strata exhibit stronger slopes
  in partial dependence plots, indicating greater sensitivity to PM₂.₅.

## 7. Limitations and Potential Flaws

- **Temporal Granularity**: Annual data obscure seasonal peaks and acute
  exposures.
- **Spatial Aggregation**: Country averages mask subnational hotspots and
  regional inequalities.
- **Ecological Fallacy**: Country-level analysis may not reflect individual
  exposure and health risks.
- **Omitted Variables**: Models do not control for all confounders (e.g.,
  smoking, healthcare quality, other pollutants).
- **Data Accuracy**: Both PM₂.₅ and DALY datasets are modeled estimates and
  carry uncertainty.

## 8. Alternative Approaches

- **Mixed-Effects Models**: Use random intercepts/slopes to account for
  unobserved heterogeneity.
- **Panel & Time-Series Methods**: Fixed-effects or distributed-lag panel models
  for dynamic response control.
- **Spatial Statistics**: Spatial panel models to capture intra-country
  variation and autocorrelation.
- **Explainable ML**: Apply SHAP or partial dependence plots to interpret
  non-linear models.

## 9. Conclusion & Policy Implications

Our analysis shows that SDI is the strongest predictor of national DALY burdens,
with PM₂.₅ providing a consistent secondary impact—especially in low- and
medium-SDI countries.

**Key Takeaways**:

- **Development Matters Most**: Higher SDI leads to lower DALYs and faster
  health improvements.
- **Pollution Persists**: PM₂.₅ still correlates with disease burden after
  adjusting for SDI.
- **Equity Focus**: Less-developed regions show higher pollution sensitivity.

---

## Comparing Two Modeling Approaches: With and Without SDI

## Introduction

This section compares two modeling approaches to understand what drives
variations in DALYs across countries. The original model relied on
country-specific identifiers, while the revised model introduced SDI as a more
meaningful explanatory variable.

The goal was to move beyond identifying which countries have high or low DALYs
and instead uncover **why** these differences exist. This shift enabled model
evaluation based on both predictive accuracy and explanatory power.

## Key Differences Between Models

### Model 1: Country Dummy Variables (Old model)

- **Mechanism**: Hundreds of binary country indicators (e.g., `country_USA`,
  `country_China`) serve as fixed effects.
- **Effect**: Model memorizes each country's average DALY, absorbing unmeasured
  national characteristics.
- **Result**: Artificially high R² (~0.98–0.99) due to overfitting.
- **Limitation**: Cannot generalize to new countries; offers no explanation for
  observed differences.

### Model 2: Socio-Demographic Index (New model)

- **Mechanism**: Replaces country dummies with a single SDI variable.
- **Effect**: Forces model to learn how development level affects health
  outcomes.
- **Result**: Lower but more realistic R² (0.65–0.79), capturing true predictive
  signal.
- **Strength**: Offers generalizable insights across geographies.

## Comparison Table

<!-- markdownlint-disable MD013 -->

| Feature                 | Old Model (Country Dummies)               | New Model (with SDI)               |
|-------------------------|-------------------------------------------|------------------------------------|
| Country-Specific Factor | ~200 binary dummy variables               | One continuous variable (SDI)      |
| Model Goal              | Memorize baseline & predict annual changes| Link development/pollution to DALYs|
| Key Insight             | Identifies "what" (high vs. low DALY)     | Explains "why" DALYs vary          |
| Generalizability        | Very poor                                 | Good                               |
| Risk of Overfitting     | Extremely high                            | Much lower                         |

<!-- markdownlint-enable MD013 -->

## Why Random Forest Performs Best in the New Model

In the old model, Linear Regression performed well because the dummy variables
made the task artificially simple. In the new model, Random Forest shines by
capturing the complex, non-linear relationships between development, pollution,
and health.

**Conclusion**: The drop in R² is not a failure. It reflects a shift from an
overfit, memorization-based model to one that offers real-world insights and
generalizability.
