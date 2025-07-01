# Dataset

This research uses two primary datasets to analyze the relationship between long-term
ambient PM₂.₅ exposure and public health outcomes across countries from 2010 to 2019,
with an additional exploratory component on COVID-19 mortality outcomes.

## 1. Air Pollution Dataset

This dataset provides annual average concentrations of PM2.5 (in µg/m³) for urban
areas by country from 2010 to 2019. Values are population-weighted and reported at
the country level. It serves as SDG Indicator 11.6.2, used for tracking urban air
quality globally.

### Source

World Health Organization (WHO) – Global Health Observatory

[Air pollution: concentrations of fine particulate matter (PM2.5), SDG 11.6.2](https://www.who.int/data/gho/data/indicators/indicator-details/GHO/concentrations-of-fine-particulate-matter-(pm2-5))

### Method of Measurement

PM2.5 concentrations are regularly measured using fixed-site, population-oriented
monitoring stations located within metropolitan areas. High-quality data from all
monitors in a given area are averaged to produce a single, representative estimate
of PM2.5 concentration for that location.

### Structure

Each row in the dataset represents PM2.5 data for a specific **country** and **year**.

#### Key Columns

- **`IndicatorCode`** / **`Indicator`**: Identifies the metric —
  *concentrations of fine particulate matter (PM2.5)*.
- **`Location`**: Name of the country (e.g., *Kenya*, *Brazil*).
- **`ParentLocation`**: The broader region or continent
  (e.g., *Africa*, *Americas*).
- **`Period`**: The year the data was collected (e.g., *2019*).
- **`IsLatestYear`**: Boolean flag indicating if it's the most recent data
  (`True` or `False`).
- **`FactValueNumeric`**: Estimated PM2.5 concentration in **µg/m³**.
- **`FactValueNumericLow`** / **`FactValueNumericHigh`**: Lower and upper
  bounds of the estimate.
- **`Value`**: Text version of the estimate with its range,
  e.g., `10.01 [6.29–13.74]`.
- **`Language`**: Language of the record (`EN` for English).
- **`DateModified`**: Date the data entry was last updated.

#### Additional Notes

- The data is based on **population-oriented, fixed-site monitors** in
  **urban/metropolitan areas**.
- Some columns (e.g., `Dim2`, `Dim3`, `FactComments`) are unused and contain
  no values in this dataset.
- Measurements reflect **annual average concentrations**.

### Flaws and limitations

- While data quality for urban and rural populations is generally good in
  high-income countries, it can be relatively poor in some low- and
  middle-income areas.
- The definition of "urban" and "rural" can vary significantly
  between countries.
- The use of national population-weighted averages may increase uncertainty.
  This method can smooth out regional differences and potentially underestimate
  pollution levels in specific high-exposure locations, especially in large or
  highly diverse countries.

### Dataset Recreation

This dataset is easily downloadable in CSV format from the following link:  
[Air pollution: concentrations of fine particulate matter (PM2.5), SDG 11.6.2](https://www.who.int/data/gho/data/indicators/indicator-details/GHO/concentrations-of-fine-particulate-matter-(pm2-5))  
It contains country-level, population-weighted annual averages for urban PM2.5 concentrations.

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
| `Age Group`  | Usually “All Ages” unless further breakdowns are selected  |

This study focuses on the following:

#### Cardiovascular Diseases

- Ischemic Heart Disease (IHD)  
- Stroke

#### Respiratory Diseases

- Chronic Obstructive Pulmonary Disease (COPD)  
- Lower Respiratory Infections (LRI)

#### COVID-19 Mortality

- Included for exploratory analysis only (2020–2021)

#### Additional Notes About the Dataset

- All estimates are **age-standardized** and **sex-disaggregated**.
- For consistency with the PM2.5 dataset, this study uses:
  - **All Ages**
  - **Both Sexes**

### Flaws and Limitations

- In countries with weak health infrastructure, estimates rely heavily on modeling.
  This increases uncertainty (wider confidence intervals).
- COVID-19 mortality may be underreported due to testing gaps or attribution issues.
- DALYs and death rates may overlap or reflect indirect or multi-cause outcomes.

### Recreation of Dataset

To recreate this dataset:

1. Visit: <https://vizhub.healthdata.org/gbd-results/>
2. Set the following parameters stated in the structure above appropriately
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

A full description of the variables in this file is available in our Data Dictionary
