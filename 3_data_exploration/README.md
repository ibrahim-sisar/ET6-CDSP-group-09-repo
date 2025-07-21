<h1 style="display: flex; align-items: center;">
  Data Exploration
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

### [`covid_deaths_pm25_sdi_eda.ipynb`](covid_deaths_pm25_sdi_eda.ipynb)

- **Dataset**: `final_merged_covid_sdi_pm2.5.csv`
- **Content**:
  - Explored and visualized the cleaned, merged dataset combining COVID-19 death
  rates, PM2.5 concentrations, and Socio-Demographic Index (SDI).

  - Conducted correlation analysis to investigate potential relationships between
SDI, PM2.5 exposure, and COVID death rate.
  - Created visual summaries (heatmaps, scatter plots, etc.) to highlight trends
  and outliers.

### [`pm25_sdi_eda.md`](pm25_sdi_eda.md)

This Markdown file introduces the folder containing the exploratory analysis of
our final dataset.

- **Dataset**: `clean_merged_data.csv`
- **Content**:
  - Final dataset merging PM₂.₅, SDI, and health burdens for diverse countries (2010–2019).
  - Focused exploration of trends in exposure and associated disease burdens.
  - Summary statistics and exploratory figures linking exposure and burden.
  - Visualizations: bar charts, heatmaps, scatter plots, and correlation matrix.

---

## 📊 Figures and Outputs

If you'd like a clear overview of the scriptsun in the exploratory notebooks,
you can find all the generated figures and outputs [The link](all_figures)

---

## ⚠️ Reproducibility Notice

- These scripts **do not modify** any files in `0_datasets/`.
- All analysis is **exploratory only**.
- Anyone cloning the repository can rerun these files for identical outputs.
