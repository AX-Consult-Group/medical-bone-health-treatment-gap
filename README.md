# Bone Health Project
# Phase 1 – Treatment Gap - NHANES 2005–2006 

This repository contains a public, reproducible analysis examining gaps in age-based osteoporosis screening using data from the **NHANES 2005–2006** cohort. The analysis focuses on identifying individuals at high bone-health risk who are not captured by current age-based screening criteria.

<img width="3585" height="2381" alt="visual_design_summary" src="https://github.com/user-attachments/assets/d933f546-18e2-4bb6-a5ff-069883574aab" />

---

## What this analysis shows

- The proportion of the population that is **screening-eligible** under current age-based guidelines  
- The proportion classified as **high bone-health risk** based on bone density and clinical/lifestyle proxies  
- The size and characteristics of the **missed high-risk population** (high risk but not screening-eligible)  
- How alternative screening scenarios (age expansion and risk-proxy triggers) reduce missed high-risk cases  
- Segment-level patterns by age, sex, and race/ethnicity, including equity guardrails  

---

## Key concepts

The analysis focuses on three overlapping groups:

1. **Screening-eligible individuals** (based on age and sex criteria)
2. **High bone-health risk individuals** (based on DXA lumbar spine T-scores and clinical/lifestyle factors)
3. **Missed high-risk individuals**, defined as those at high risk who are not screening-eligible

The primary objective is to quantify and illustrate the size of the missed high-risk group and explore how alternative screening logic could reduce this gap.

---

## Data sources

The following data sets (`.XPT`) files from the **2005–2006 NHANES cycle** are required:

- **Demographics (DEMO_D.XPT)**  
  2005–2006 Demographics Data – Continuous NHANES  
  https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Demographics&CycleBeginYear=2005

- **Body Measures (BMX_D.XPT)**  
  2005–2006 Examination Data – Continuous NHANES  
  https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Examination&Cycle=2005-2006

- **Dual Energy X-ray Absorptiometry (DXX_D.XPT)**  
  1999–2006 DXA Multiple Imputation Data Files  
  https://wwwn.cdc.gov/Nchs/Nhanes/Dxa/Dxa.aspx

- **Osteoporosis Questionnaire (OSQ_D.XPT)**  
  2005–2006 Questionnaire Data – Continuous NHANES  
  https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Questionnaire&CycleBeginYear=2005

- **Smoking Questionnaire (SMQ_D.XPT)**  
  2005–2006 Questionnaire Data – Continuous NHANES  
  https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Questionnaire&CycleBeginYear=2005

- **Physical Activity Questionnaire (PAQ_D.XPT)**  
  2005–2006 Questionnaire Data – Continuous NHANES  
  https://wwwn.cdc.gov/nchs/nhanes/search/datapage.aspx?Component=Questionnaire&CycleBeginYear=2005

All data were merged using the NHANES respondent identifier (`SEQN`).

---

## Methods (high level)

- Relevant variables were selected from each dataset based on clinical relevance  
- Lumbar spine T-scores were used to classify bone density status  
- High bone-risk status was defined using a combination of DXA results and risk proxies  
- Missing data were assessed and handled conservatively to avoid inflating risk estimates  
- Multiple screening scenarios were evaluated to estimate potential reductions in missed high-risk cases  
- Results were summarized using tables and interpretable visualizations  

---

## Important notes

- This analysis uses **real NHANES data**
- No clinical decisions should be made based on this analysis  
- Screening rules and thresholds are simplified proxies, not clinical recommendations  
- Minor differences from published prevalence estimates may occur due to analytic choices and exclusions  

---

## How to view the report

The full rendered report is available via **GitHub Pages**:

https://ax-consult-group.github.io/medical-bone-health-treatment-gap/poe_bone_health.html

---

## R packages used

The analysis was conducted in R using the following packages:

- **Data manipulation & pipelines**  
  - magrittr  
  - tidyverse  
  - dplyr  
  - tibble  
  - janitor  

- **Data import & export**  
  - haven  
  - readxl  
  - writexl  

- **Analysis & utilities**  
  - psych  
  - scales  

- **Visualisation & reporting**  
  - ggplot2  
  - knitr  
  - kableExtra

RStudio 2026.01.0+392 "Apple Blossom" Release (49fbea7a09a468fc4d1993ca376fd5b971cb58e3, 2026-01-04) for windows
Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) RStudio/2026.01.0+392 Chrome/140.0.7339.249 Electron/38.7.2 Safari/537.36, Quarto 1.8.25 

---

