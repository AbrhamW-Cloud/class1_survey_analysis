# Among U.S. adults in NHANES (2017–2018), how is vitamin D status associated with fasting serum insulin and glucose levels, after adjusting for age, sex, and race/ethnicity?

## Project Description
This repository investigates the association between serum 25-hydroxyvitamin D [25(OH)D] status and fasting biomarkers of glycemia (serum insulin and glucose) among U.S. adults using NHANES 2017–2018 data. The analysis will account for NHANES' complex, multistage survey design and adjust for key confounders (age, sex, race/ethnicity). Findings aim to contextualize vitamin D's relationship with insulin resistance and glycemic control in a nationally representative sample.

## Dataset
- **Name:** NHANES 2017–2018
- **Key files likely used:**
  - Demographics (`DEMO_J.XPT`)
  - Vitamin D (`VID_J.XPT`)
  - Fasting insulin (`INS_J.XPT`)
  - Fasting glucose (`GLU_J.XPT`)
  - Fasting questionnaire & weights (`FASTQ_J.XPT`, includes `WTSAF2YR`)
- **Merge key:** `SEQN`

## Research Questions & Outcomes
- **Exposure:** Serum 25(OH)D (continuous; and categories <20, 20–29, ≥30 ng/mL).
- **Outcomes:** Fasting insulin (µU/mL), fasting glucose (mg/dL).
- **Covariates:** Age, sex, race/ethnicity (NHANES categories).

### Planned Analyses (pick & refine)
1. Survey-weighted linear regression (primary)
2. Check nonlinearity (restricted cubic splines)
3. Sensitivity: add BMI, season, smoking, PA; test trend with categories
4. Effect modification by sex or race/ethnicity

## Handling Complex Survey Design
Use `WTSAF2YR` (fasting subsample weight) with `SDMVSTRA`, `SDMVPSU`. Fit models with `survey` / `srvyr`.

## How to Run
1) Place NHANES XPT files in `/data`.  
2) Open `/code/analysis_code.Rmd`.  
3) Knit to produce tables/figures in `/output`.

## Files Included
- `README.md`
- `code/analysis_code.Rmd` (to be created)
- `data/` (NHANES XPT files)
- `output/` (results)

## Author
- Name: Abrham Azale
- Course: Fall_2025.PHCC.6009.01 - Advanced Data Analysis
- Date: November 2025

