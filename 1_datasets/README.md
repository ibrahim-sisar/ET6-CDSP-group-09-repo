# Dataset

This research uses three primary datasets to analyze the relationship between long-term
ambient PM2.5 exposure and public health outcomes across countries from 2010 to 2019,
with an additional exploratory component on COVID-19 mortality outcomes.

- Air Pollution Dataset (PM2.5)
- Socio-Demographic Index Dataset (SDI)
- Global Burden of Disease Dataset (GBD)

## 1. Air Pollution Dataset (PM2.5)

This dataset provides annual average concentrations of PM2.5 (in µg/m³) for urban
areas by country from 2010 to 2019. Values are population-weighted and reported at
the country level. It serves as SDG Indicator 11.6.2, used for tracking urban air
quality globally.

### PM2.5 Dataset Source

World Health Organization (WHO) – Global Health Observatory

[Air pollution: concentrations of fine particulate matter (PM2.5), SDG 11.6.2](https://www.who.int/data/gho/data/indicators/indicator-details/GHO/concentrations-of-fine-particulate-matter-(pm2-5))

### PM2.5 Method of Measurement

PM2.5 concentrations are regularly measured using fixed-site, population-oriented
monitoring stations located within metropolitan areas. High-quality data from all
monitors in a given area are averaged to produce a single, representative estimate
of PM2.5 concentration for that location.

### PM2.5 Dataset Structure

Each row in the dataset represents PM2.5 data for a specific **country** and **year**.

#### PM2.5 Dataset Columns

| Column | Description |
|--------|-------------|
| `IndicatorCode` | Code for the PM2.5 indicator |
| `Indicator` | Description of the PM2.5 indicator |
| `ValueType` | Type of value (e.g., estimate, measured) |
| `ParentLocationCode` | Code for the parent region (e.g., continent) |
| `ParentLocation` | Name of the parent region (e.g., Africa) |
| `Location type` | Type of location (e.g., country, region) |
| `SpatialDimValueCode` | Code identifying the location |
| `Location` | Country or area name |
| `Period type` | Type of time period (e.g., year) |
| `Period` | Year the data was collected |
| `IsLatestYear` | Boolean indicating if this is the most recent data |
| `Dim1 type` | First dimension type (e.g., area type) |
| `Dim1` | Value of the first dimension (e.g., Total, Urban) |
| `Dim1ValueCode` | Code for `Dim1` |
| `FactValueNumeric` | Estimated PM2.5 concentration in µg/m³ |
| `FactValueNumericLow` | Lower bound of PM2.5 estimate |
| `FactValueNumericHigh` | Upper bound of PM2.5 estimate |
| `Value` | Textual representation of estimate with range |
| `Language` | Language of the record (e.g., EN) |
| `DateModified` | Last date the record was updated |

#### Additional Notes on PM2.5 Dataset

- The data is based on **population-oriented, fixed-site monitors** in
  **urban/metropolitan areas**.
- Empty columns: `Dim2 type`, `Dim2`, `Dim2ValueCode`, `Dim3 type`, `Dim3`,
  `Dim3ValueCode`, `DataSourceDimValueCode`, `DataSource`, `FactValueNumericPrefix`,
  `FactValueUoM`, `FactValueNumericLowPrefix`, `FactValueNumericHighPrefix`,
  `FactValueTranslationID`, `FactComments`.

- Measurements reflect **annual average concentrations**.

### PM2.5 Dataset Flaws and limitations

- While data quality for urban and rural populations is generally good in
  high-income countries, it can be relatively poor in some low- and
  middle-income areas.
- The definition of "urban" and "rural" can vary significantly
  between countries.
- The use of national population-weighted averages may increase uncertainty.
  This method can smooth out regional differences and potentially underestimate
  pollution levels in specific high-exposure locations, especially in large or
  highly diverse countries.

### PM2.5 Dataset Recreation

This dataset is easily downloadable in CSV format from the source link above.
It contains country-level, population-weighted annual averages for urban PM2.5 concentrations.

## Socio-Demographic Index (SDI) Dataset

This dataset provides annual Socio-demographic Index (SDI) values from 1950 to
2021 across global, regional, and national locations. SDI is a composite metric
used to capture a location’s level of development based on income, education,
and fertility. It enables analysis of health outcomes relative to socio-economic
progress.

### SDI Dataset Source

Institute for Health Metrics and Evaluation (IHME) – Global Burden of Disease Study
2021

[Global Burden of Disease Study 2021 (GBD 2021) Socio-demographic Index (SDI) 1950–2021](https://ghdx.healthdata.org/record/global-burden-disease-study-2021-gbd-2021-socio-demographic-index-sdi-1950%E2%80%932021)

### SDI Method of Measurement

SDI is calculated as the geometric mean of three components:

- **Total fertility rate** under age 25
- **Mean education** for those aged 15 or older
- **Lag-distributed income** per capita

Each component is normalized between 0 and 1, and the final SDI value ranges from
0 (least developed) to 1 (most developed).

### SDI Dataset Structure

Each row in the dataset represents SDI data for a specific **location**, **year**.

#### Key Columns

| Column | Description |
|--------|-------------|
| `covariate_name_short` | Abbreviation of the indicator (always `sdi`) |
| `location_id` | Numeric identifier for the geographic location |
| `location_name` | Name of the country, region, or global aggregate |
| `year_id` | Year the SDI value corresponds to |
| `age_group_id` | ID representing the age group |
| `age_group_name` | Name of the age group (e.g., All Ages) |
| `sex_id` | Numeric identifier for sex (1=Male, 2=Female, 3=Both) |
| `sex` | Sex of the population (Male, Female, Both) |
| `mean_value` | Estimated SDI value (0–1) |
| `lower_value` | Lower bound of the estimate |
| `upper_value` | Upper bound of the estimate |

#### Additional Notes

- The dataset spans from **1950 to 2021**, allowing for long-term trend analysis.
- Only uses all ages and both sexes for the estimates
- Measurements reflect **normalized development indices**.

### Flaws and limitations

- Although SDI is a useful summary measure, it may not capture nuanced inequalities
  within countries or across subpopulations.
- Values prior to 1990 may be based on extrapolations or indirect estimation.
- Uniformity of age/sex dimensions, while simplifying use, does not imply meaningful
  variability across those categories in this dataset.

### Dataset Recreation

This dataset is downloadable in CSV format from the IHME Global Health Data Exchange
(source link provided above).

## 2. Health Dataset — IHME Global Burden of Disease (GBD)

This dataset provides annual estimates of the burden of cardiovascular and
respiratory diseases across countries from 2010 to 2019, with additional data on
COVID-19 mortality for 2020–2021. It includes **standardized health metrics** that
allow for meaningful comparison across countries regardless of population size or
healthcare system.

### Dataset Source

Institute for Health Metrics and Evaluation (IHME)  
[Global Burden of Disease (GBD) Results Tool](https://vizhub.healthdata.org/gbd-results/)

### Measurement Method

GBD estimates are derived using:

- Vital registration systems  
- Household surveys  
- Hospital records  
- Epidemiological studies  
- Statistical modeling

When direct data is missing or incomplete, GBD uses **Bayesian meta-regression**
techniques (`DisMod-MR`) to estimate values based on related and regional data.This
ensures internally consistent estimates, even in countries with weak health surveillance
systems.

### Dataset Structure

Each row represents the burden of a specific disease for a particular country and
year.

#### Key Columns of Datasets

| Column       | Description                                               |
|--------------|-----------------------------------------------------------|
| `Location`   | Country name (e.g., Kenya, Brazil)                        |
| `Year`       | Calendar year of the estimate (e.g., 2015)                |
| `Cause`      | Specific disease (e.g., Ischemic heart disease, Stroke)   |
| `Metric`     | What’s being quantified (e.g., number, rate per 100,000)  |
| `Measure`    | Type of measure (e.g., Deaths, DALYs, Mortality rate)     |
| `Sex`        | Male, Female, or Both                                     |
| `GBD Estimate`| By cause of death or risk factor                 |
| `Age Group`  | Age-standardized used for comparative analysis |

This study focuses on the following:

- Cardiovascular Diseases with focus on stroke
- Chronic Respiratory Diseases
- COVID-19 Mortality, a sub dataset included for exploratory analysis only (2020–2021).

#### Additional Notes About the Dataset

- **Measures:**
  - **DALYs**: Combined years lost due to death (YLLs) and disability (YLDs)  
  - **YLLs**: Years of life lost due to premature mortality  
  - **YLDs**: Years lived with disability  
  - **Deaths**: Number of deaths from the cause

- **Metrics:**
  - **Number**: Absolute count of cases  
  - **Rate**: Per 100,000 population  
  - **Percent**: Proportion relative to total health burden

- The data uses **age-standardized** rates to control for demographic differences.

### Flaws and Limitations

- In countries with weak health infrastructure, estimates rely heavily on modeling.
  This increases uncertainty (wider confidence intervals).
- COVID-19 mortality may be underreported due to testing gaps or attribution issues.
- DALYs and death rates may overlap or reflect indirect or multi-cause outcomes.

### Recreation of Dataset

To recreate this dataset:

1. Visit: <https://vizhub.healthdata.org/gbd-results/>
2. Set the parameters stated in the structure above appropriately
3. Click **"Download Results"** to export the data as a CSV file.

## Public Hosting of Prepared Dataset

For this milestone, we are hosting our prepared dataset directly within this GitHub
repository. As our final dataset's size is under 100MB, this method provides the
most direct and efficient access for review and reproducibility.

To ensure our data preparation process is transparent, we have organized our data
into the following structure:

1. Raw Datasets: This folder contains the original, untouched data as collected
   from our sources.
   - Location: [`raw_datasets`](../1_datasets/raw_datasets)

1. Cleaned Datasets: This folder holds intermediate datasets and the scripts used
   to process and clean the raw data. This shows our step-by-step workflow.
   - Location: [`cleaned_datasets`](../1_datasets/cleaned_datasets)

1. Final Dataset: This folder contains the final **prepared**, analysis-ready dataset
   that is the primary deliverable for this milestone.
   - Location: [`final_datasets`](../1_datasets/final_datasets)
