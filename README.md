
# Class 1 Survey Data Analysis

## Project Description
This repository investigates the association between serum 25-hydroxyvitamin D (25(OH)D) and fasting biomarkers of glycemia (serum insulin and glucose) among U.S. adults using NHANES 2017–2018. The analysis accounts for NHANES’s complex, multistage survey design and adjusts for key confounders (age, sex, race/ethnicity). The goal is to contextualize vitamin D’s relationship with insulin resistance and glycemic control.

## Files Included
- `nhanes_2017_2018/` – folder containing the XPT files actually used
  - `demo_j.xpt` (demographics)
  - `vid_j.xpt` (vitamin D)
  - `ins_j.xpt` (fasting insulin)
  - `glu_j.xpt` (fasting glucose)
  - `fastq_j.xpt` (fasting questionnaire with weights: `WTSAF2YR`)
- `code/analysis_code.Rmd` – main R Markdown with survey-weighted analyses
- `output/` – tables and figures produced by the Rmd
- `README.md` – this file

## What the Code Does
- Reads NHANES 2017–2018 XPT files and merges them by `SEQN`
- Applies fasting subsample weights (`WTSAF2YR`) and survey design variables (`SDMVSTRA`, `SDMVPSU`)
- Creates analysis variables for 25(OH)D (continuous and categories: <20, 20–29, ≥30 ng/mL)
- Produces descriptive statistics by vitamin D category
- Fits survey-weighted linear regression models:
  - Outcome: fasting insulin (µIU/mL) and fasting glucose (mg/dL)
  - Exposure: 25(OH)D (continuous and categorical)
  - Covariates: age, sex, race/ethnicity (with sensitivity models adding BMI, smoking, physical activity)
- Checks nonlinearity (restricted cubic splines) and conducts subgroup/sensitivity analyses
- Exports publication-ready tables/figures to `output/`

## How to Run the Code
1. Clone or download this repository.
2. Place NHANES XPT files inside `nhanes_2017_2018/` (keep the lowercase, underscore naming).
3. Open `code/analysis_code.Rmd` in RStudio.
4. Install/load required packages: `haven`, `tidyverse`, `srvyr`, `survey`, `rms`, `tableone`, `gt`.
5. Knit the Rmd to generate the results in `output/`.

## Author
- Name: Abrham Azale
- Course: Fall_2025.PHCC.6009.01 - Advanced Data Analysis
- Date: November 2025


