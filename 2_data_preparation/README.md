<h1 style="display: flex; align-items: center;">
  Data Cleaning And Preparation
  <img src="../notes/images/data_cleaning.gif" alt="data" style="height:50px; margin-left:10px;">
</h1>

This folder contains all Python scripts and Jupyter notebooks used to clean,
reformat, and prepare raw datasets for our research project:

## 📌 Purpose  

All scripts in this folder:

- Read original datasets from the [`/1_datasets/raw_datasets`](../1_datasets/raw_datasets)

- Perform cleaning, filtering, transformation, and formatting steps

- Output processed datasets to [`/1_datasets/cleaned_datasets`](../1_datasets/cleaned_datasets)
with clear, descriptive filenames

- Output final analysis-ready merged datasets to [`/1_datasets/final_datasets`](../1_datasets/final_datasets)

## 📄 Scripts Overview

### [`pm25_annual_concentration_data_cleaning.ipynb`](pm25_annual_concentration_data_cleaning.ipynb)

Cleans the WHO ambient PM₂.₅ dataset:

- Filters for years 2010–2019  
- Selects 25 target countries  
- Handles missing or unreliable values  
- Renames and formats columns for merging  

➡️ Output:  
[`cleaned_pm25_data.csv`](../1_datasets/cleaned_datasets/cleaned_pm25_data.csv)

---

### [`covid_death_data_cleaning.ipynb`](covid_death_data_cleaning.ipynb)

Processes IHME GBD data on COVID-19 mortality:

- Filters deaths attributed to COVID-19  
- Focuses on age group 15–49  
- Keeps only years 2020 and 2021  
- Filters for the 25 study countries  
- Cleans and renames for merging  

> Used to explore links between long-term PM₂.₅ exposure and COVID-19 deaths  

➡️ Output:  
[`cleaned_death.csv`](../1_datasets/cleaned_datasets/cleaned_death.csv)

---

### [`cleaned_sdi_by_country_year_2010_2019.ipynb`](cleaned_sdi_by_country_year_2010_2019.ipynb)

Prepares Socio-Demographic Index (SDI) data:

- Extracts mean SDI values by country and year  
- Filters for 25 study countries  
- Prepares for grouping/stratification in analysis  

➡️ Output:  
[`cleaned_sdi_data.csv`](../1_datasets/cleaned_datasets/cleaned_sdi_data.csv)

---

### [`clean_gbd_health_outcomes.ipynb`](clean_gbd_health_outcomes.ipynb)

Processes GBD data on disease burden:

- Focuses on cardiovascular and respiratory diseases  
- Filters metrics where PM₂.₅ is a contributing risk  

➡️ Output:  
[`cleaned_gbd_resp_cardio.csv`](../1_datasets/cleaned_datasets/cleaned_gbd_resp_cardio.csv)

---

### [`merge_sdi_pm25.ipynb`](merge_sdi_pm25.ipynb)

Creates intermediate merged dataset:

- Combines SDI and PM₂.₅ data (2010–2019)  
- Merges on Country and Year  
- Used as base for merging with GBD and COVID data  

➡️ Output:  
[`merged_sdi_pm25_data.csv`](../1_datasets/cleaned_datasets/merged_sdi_pm25_data.csv)

---

### [`merge_final_gbd_pm25.ipynb`](merge_final_gbd_pm25.ipynb)

Merges disease burden data with PM₂.₅ and SDI:

- Starts from `merged_sdi_pm25_data.csv`  
- Adds GBD metrics data (2010–2019)  
- Merges on Country and Year  
- Prepares final dataset for pre-COVID burden analysis  

➡️ Output:  
[`final_merged_gbd_pm25.csv`](../1_datasets/final_datasets/final_merged_gbd_pm25.csv)

---

### [`merge_final_with_covid.ipynb`](merge_final_with_covid.ipynb)

Merges COVID-19 mortality with PM₂.₅ and SDI:

- Starts from `merged_sdi_pm25_data.csv`  
- Adds COVID-19 death data (ages 15–49, 2020–2021)  
- Enables analysis of long-term exposure and COVID deaths  

➡️ Output:  
[`final_merged_with_covid.csv`](../1_datasets/final_datasets/final_merged_with_covid.csv)
