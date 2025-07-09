<h1 style="display: flex; align-items: center;">
  Data Cleaning And Preparation
  <img src="../notes/images/data_cleaning.gif" alt="data" style="height:50px; margin-left:10px;">
</h1>

This folder contains all Python scripts and Jupyter notebooks used to clean,
reformat, and prepare raw datasets for our research project

## 📌 Purpose  

All scripts in this folder:

- Read original datasets from the [`/1_datasets/raw_datasets`](../1_datasets/raw_datasets)

- Perform cleaning, filtering, transformation, and formatting steps

- Output processed datasets to [`/1_datasets/cleaned_datasets`](../1_datasets/cleaned_datasets)
with clear, descriptive filenames

- Output final analysis-ready merged datasets to [`/1_datasets/final_datasets`](../1_datasets/final_datasets)

## 📄 Scripts Overview

### [`covid_deaths_sdi_pm25_all_countries.ipynb`](covid_deaths_sdi_pm25_all_countries.ipynb)

This notebook performs comprehensive data cleaning and integration across multiple
datasets:

- Cleans the WHO ambient PM₂.₅ dataset by filtering relevant years, handling
missing values, and standardizing column formats  
- Cleans the SDI (Socio-Demographic Index) dataset, including data for 2020  
- Cleans the COVID-19 deaths dataset to ensure consistency and proper formatting
- Merges all three cleaned datasets on `Country` and `Year` to produce a unified
and comprehensive dataset ready for analysis  

➡️ **Outputs:**  

- [`pm25_all_countries_cleaned.csv`](../1_datasets/cleaned_datasets/pm25_all_countries_cleaned.csv)
- [`sdi_data_2010_2019_cleaned.csv`](../1_datasets/cleaned_datasets/sdi_data_2010_2019_cleaned.csv)
- [`covid_all_countries_cleaned.csv`](../1_datasets/cleaned_datasets/covid_all_countries_cleaned.csv)
- [`final_merged_covid.csv`](../1_datasets/final_datasets/final_merged_covid.csv)
the fully merged dataset integrating all three sources  

---

### [`clean_gbd_and_merge_all.ipynb`](clean_gbd_and_merge_all.ipynb)

This notebook focuses on cleaning and merging health outcomes data with SDI and
PM₂.₅ datasets for the period **2010–2019**:

- Cleans the health outcomes dataset by filtering relevant years, handling
missing values, and standardizing column formats  
- Cleans and prepares the SDI and PM₂.₅ datasets for the same time period  
- Merges all three datasets on `Country` and `Year` to create a consolidated
dataset covering mutual countries and years  

➡️ **Outputs:**  

- [`final_sdi_pm25_gbd`](../1_datasets/final_datasets/final_sdi_pm25_gbd.csv)
— the fully merged dataset integrating health, SDI, and PM₂.₅ data  

---
