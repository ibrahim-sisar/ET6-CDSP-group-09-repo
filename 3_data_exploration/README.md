<h1 style="display: flex; align-items: center;">
  Data Cleaning And Preparation
  <img src="../notes/images/data_exploration.gif" alt="data"
  style="height:50px; margin-left:10px;">
</h1>

## 📌 Purpose

This folder contains notebooks and scripts used to **explore the cleaned datasets**
from `0_datasets/`.  
The goal is to understand the data structure and patterns without performing
inferential statistics or modifying the original data.

All scripts strictly follow the principles of open research and reproducibility.
Any visual outputs are saved in this folder or linked below.

---

## 📄 Scripts Overview

### [`explore_health_burdens_daly.ipynb`](explore_health_burdens.ipynb)

- **Dataset**: `clean_gbd_health.csv` (from `0_datasets/`)
- **Content**:
  - Explores health burden data (DALYs) attributed to ambient PM₂.₅ exposure.
  - Focus on respiratory and cardiovascular disease burdens.
  - Descriptive statistics and grouped summaries by disease, country, and year.
  - Visualizations: heatmaps and stacked bar chart plots.

### [`explore_pm25_sdi.ipynb`](explore_pm25_sdi.ipynb)

- **Dataset**: `merged_sdi_pm25_data.csv`, `cleaned_sdi_data.csv`
- **Content**:
  - Explores spatial and temporal variation in PM₂.₅ and SDI (Socio-demographic Index).
  - Descriptive distributions, pm2.5 over time by countries, distributing SDI Tiers
  - Visualizations: scatter plot, Tiers, line plots

### [`EDA_gbd_pm25_sdi.ipynb`](EDA_gbd_pm25_sdi.ipynb)

- **Dataset**: `final_gbd_pm25_sdi_data.csv`
- **Content**:
  - Final dataset merging PM₂.₅, SDI, and health burdens for 25 countries (2010–2019).
  - Focused exploration of trends in exposure and associated disease burdens.
  - Summary statistics and exploratory figures linking exposure and burden.
  - Visualizations: bar charts, heatmaps, scatter plots

---

## 📊 Figures and Outputs

If you'd like a clear overview of the scriptsun in the exploratory notebooks,
you can find all the generated figures and outputs [The link](../../3_data_exploration/figures)

---

## ⚠️ Reproducibility Notice

- These scripts **do not modify** any files in `0_datasets/`.
- All analysis is **exploratory only**.
- Anyone cloning the repository can rerun these files for identical outputs.
