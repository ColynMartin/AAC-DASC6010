# Evaluating Trustworthy Anomaly Detection in CDC COVID-19 Data

##  Project Overview
This project investigates whether anomaly detection models can reliably identify meaningful irregularities in large-scale public health data.

Using the CDC COVID-19 Case Surveillance dataset, we analyze reporting patterns over time to detect unusual observations and evaluate whether those anomalies are **statistically valid, consistent across models, and interpretable in real-world context**.

---

##  Objectives
- Detect anomalies in COVID-19 reporting data  
- Compare results across multiple anomaly detection models  
- Evaluate whether anomalies are:
  - Statistically significant  
  - Consistent across models  
  - Explainable using real-world public health events
    
---

## 👥 Team Roles

- **Colyn Martin — Data Preparation & Quality Control**
  - Data cleaning and preprocessing  
  - Feature engineering  
  - Verified data integrity and anomaly alignment  

- **Ayushi Bohra — Anomaly Detection Modeling**
  - Implemented models (Isolation Forest, LOF, One-Class SVM)  
  - Generated anomaly outputs  

- **Ananya Vakde — Analysis & Interpretation**
  - Interpreted anomaly patterns  
  - Connected results to real-world context  

---

##  Dataset

- **Source:** CDC COVID-19 Case Surveillance Public Use Dataset  
- **Type:** Observational, case-level data  
- **Time Range:** 2020–2024  
- **Original Size:** ~13–14 GB (tens of millions of records)  

The dataset used in this project was obtained from the official CDC public use surveillance dataset:

🔗 https://data.cdc.gov/Case-Surveillance/COVID-19-Case-Surveillance-Public-Use-Data/vbim-akqf/about_data

---

### ⚠️ Dataset Disclaimer

Reporting of new COVID-19 Case Surveillance data was discontinued on **July 1, 2024**.  
This dataset is no longer actively updated and represents a fixed snapshot of reported cases.

---

###  How to Obtain the Original Dataset (CDC)

1. Navigate to the dataset page (link above)  
2. Click **“Export”**  
3. Select **“Download file” → CSV format**  

--- OR ---

### Access to Our Exported Dataset

We exported a full CSV version of the dataset (February 2026) and stored it in a university OneDrive environment due to its large file size.

🔗 [Original Exported Dataset (University OneDrive)](https://studentsecuedu66932-my.sharepoint.com/:x:/r/personal/martincol25_students_ecu_edu/Documents/COVID-19_Case_Surveillance_Public_Use_Data_20260225.csv)

 Note:
- This file may require access approval due to university restrictions  
- External users may not be able to download it directly  

Please email us to request access:
- martincol25@students.ecu.edu  
- vakdea24@students.ecu.edu  
- bohraa25@students.ecu.edu  

---

###  Reproducibility Note

- A **0.5% sampled dataset** is included:
  → `0.5_cdc_case_surveillance_sample.xls`

- All analysis and results are based on this sample  
- Sampling process:
  → `Dataset & Sampling/Generation_of_0.5%_Sample.ipynb`

---

###  Important

The sample dataset preserves the statistical structure of the full dataset, ensuring:
- consistent distributions  
- meaningful anomaly detection  
- full reproducibility without needing the full dataset  

---

##  Methodology

###  Sampling Strategy
- Chunk-based sampling (~100,000 rows per chunk)  
- Randomly selected **0.5% per chunk**  
- Fixed random seed  

Final dataset: **191,662 observations**

---

###  Data Preparation
- Cleaned and standardized dataset  
- Handled missing values (categorical → "Unknown")  
- Encoded binary variables  
- Removed high-missingness features  

---

###  Feature Engineering
- Daily case counts  
- Daily case change  
- 7-day rolling average  

---

### Anomaly Detection Models
- Isolation Forest → global spikes  
- LOF → local irregularities  
- One-Class SVM → complex patterns  

Each model detected ~78 anomalies.

---

##  Validation Approach

### 1. Data & Feature Validation
- 100% of anomaly dates matched dataset  
- Features aligned correctly  

### 2. Statistical Validation
- Mean cases: ~600–780 vs. ~80–100  
- Variability: ~970 vs. ~70  

-> Indicates extreme, non-random behavior  

### 3. Cross-Model Agreement
- **32 shared anomalies across all models**  

### 4. Pattern Validation
- Top percentile values  
- Align with visible spikes  

---

##  Key Findings
- Anomalies cluster in time (not random)  
- Align with COVID surges  
- Also reflect:
  - reporting delays  
  - backlog releases  
  - data corrections  

---

##  Limitations
- Based on 0.5% sample  
- Reporting inconsistencies  
- No regional breakdown  
- Some anomalies need external validation  

---
## 📂 Repository Structure

```text
.
├── Anomaly Detection Models/
│   ├── Anomaly_Detection_Modeling.ipynb
│   ├── Validation_of_Anomalies_Detected.ipynb
│   ├── common_anomalies.xls
│   ├── isolation_forest_anomalies.xls
│   ├── lof_anomalies.xls
│   ├── svm_anomalies.xls
│
├── Data Cleaning & Preparation/
│   ├── 0.5_sample_cleaned_dataset.xls
│   ├── Cleaned_0.5_sample_dataset_workup.html
│   ├── Cleaned_0.5_sample_dataset_workup.ipynb
│
├── Data Interpretation/
│   ├── Analysis and Interpretation of Anomalies.docx
│
├── Dataset & Sampling/
│   ├── 0.5_cdc_case_surveillance_sample.xls
│   ├── Generation_of_0.5%_Sample.html
│   ├── Generation_of_0.5%_Sample.ipynb
│   ├── Justification_For_The_0.5_Percent_Sampled_Dataset.zip
│
├── Exploratory Data Analysis/
│   ├── Exploratory Data Analysis.ipynb
│
├── Feature Engineering/
│   ├── Derived_Features_Workup_Notebook.html
│   ├── Derived_Features_Workup_Notebook.ipynb
│   ├── Exploratory_Analysis_and_Feature_Preparation.ipynb
│   ├── derived_features_sample.xls
│
├── Final Presentation/
│   ├── Big Data Analytics – Final Project PPT.pptx
│
├── Model Comparison/
│   ├── Analysis_and_Interpretation_of_Anomaly_Detection_Models.html
│   ├── Analysis_and_Interpretation_of_Anomaly_Detection_Models.ipynb
│
├── Project Workflow & Overview/
│   ├── Project_Workflow_Timeline_and_Tasks.docx
│
└── README.md
```
---

## Core Workflow Structure:
Sampling → Cleaning → EDA → Feature Engineering → Modeling → Validation → Interpretation

---

##  Step-by-Step Reproduction Guide

This project can be recreated from the provided files by following the workflow below.

### 1. Obtain the full CDC dataset or use the provided sample
You have two options:

**Option A: Download from CDC**
1. Go to the CDC COVID-19 Case Surveillance Public Use Dataset page:  
   `https://data.cdc.gov/Case-Surveillance/COVID-19-Case-Surveillance-Public-Use-Data/vbim-akqf/about_data`
2. Click **Export**
3. Select **Download file → CSV**

**Option B: Request our exported full CSV**
- Our exported CSV is stored in a university OneDrive environment and may require permission.
- Contact:
  - `martincol25@students.ecu.edu`
  - `vakdea24@students.ecu.edu`
  - `bohraa25@students.ecu.edu`

**Option C: Use the provided 0.5% sample**
- For full reproducibility of this repo, you can use:
  - `Dataset & Sampling/0.5_cdc_case_surveillance_sample.xls`

---

### 2. Generate or review the 0.5% sampled dataset
Run or review:

- `Dataset & Sampling/Generation_of_0.5%_Sample.ipynb`

This notebook:
- reads the full CDC dataset in chunks
- applies chunk-based random sampling
- uses a fixed random seed for reproducibility
- produces the sampled dataset

Output:
- `Dataset & Sampling/0.5_cdc_case_surveillance_sample.xls`

Supporting documentation:
- `Dataset & Sampling/Generation_of_0.5%_Sample.html`
- `Dataset & Sampling/Justification_For_The_0.5_Percent_Sampled_Dataset.zip`

---

### 3. Clean and prepare the sampled dataset
Run:

- `Data Cleaning & Preparation/Cleaned_0.5_sample_dataset_workup.ipynb`

This notebook:
- standardizes variable names and formats
- converts date fields for time-based analysis
- handles missing categorical values using `"Unknown"`
- recodes binary variables
- removes high-missingness variables

Output:
- `Data Cleaning & Preparation/0.5_sample_cleaned_dataset.xls`

Reference file:
- `Data Cleaning & Preparation/Cleaned_0.5_sample_dataset_workup.html`

---

### 4. Perform exploratory data analysis
Run:

- `Exploratory Data Analysis/Exploratory Data Analysis.ipynb`

This notebook is used to:
- examine variable distributions
- inspect temporal patterns
- understand data quality and class imbalance
- support the decision-making for feature engineering and anomaly analysis

---

### 5. Create derived features for modeling
Run:

- `Feature Engineering/Derived_Features_Workup_Notebook.ipynb`

This notebook creates the main modeling features:
- daily case counts
- daily case change
- 7-day rolling average

Output:
- `Feature Engineering/derived_features_sample.xls`

Additional related files:
- `Feature Engineering/Derived_Features_Workup_Notebook.html`
- `Feature Engineering/Exploratory_Analysis_and_Feature_Preparation.ipynb`

---

### 6. Run anomaly detection models
Run:

- `Anomaly Detection Models/Anomaly_Detection_Modeling.ipynb`

This notebook:
- loads the engineered features
- trains the three anomaly detection models:
  - Isolation Forest
  - Local Outlier Factor (LOF)
  - One-Class SVM
- generates anomaly predictions for each model
- identifies overlapping anomalies across models

Outputs:
- `Anomaly Detection Models/isolation_forest_anomalies.xls`
- `Anomaly Detection Models/lof_anomalies.xls`
- `Anomaly Detection Models/svm_anomalies.xls`
- `Anomaly Detection Models/common_anomalies.xls`

---

### 7. Validate detected anomalies
Run:

- `Anomaly Detection Models/Validation_of_Anomalies_Detected.ipynb`

This notebook validates anomaly results by checking:
- anomaly dates match the reconstructed dataset
- derived features align correctly
- anomaly days differ statistically from normal days
- overlapping anomalies across all three models represent high-confidence results

This step supports the project’s trustworthiness claim.

---

### 8. Compare and interpret model outputs
Review:

- `Model Comparison/Analysis_and_Interpretation_of_Anomaly_Detection_Models.ipynb`
- `Model Comparison/Analysis_and_Interpretation_of_Anomaly_Detection_Models.html`

These files help summarize:
- model behavior
- differences in anomaly capture
- cross-model overlap

---

### 9. Review the real-world interpretation of anomalies
Open:

- `Data Interpretation/Analysis and Interpretation of Anomalies.docx`

This document connects anomaly patterns to possible public health explanations, such as:
- reporting delays
- backlog releases
- outbreak surges
- data corrections

---

##  Recommended Execution Order

For the cleanest recreation of the workflow, use this order:

1. `Generation_of_0.5%_Sample.ipynb`
2. `Cleaned_0.5_sample_dataset_workup.ipynb`
3. `Exploratory Data Analysis.ipynb`
4. `Derived_Features_Workup_Notebook.ipynb`
5. `Anomaly_Detection_Modeling.ipynb`
6. `Validation_of_Anomalies_Detected.ipynb`
7. `Analysis_and_Interpretation_of_Anomaly_Detection_Models.ipynb`
8. `Analysis and Interpretation of Anomalies.docx`

---

##  Reproducibility Notes

- The full CDC dataset is very large, so this project uses a **0.5% sampled dataset** for practical reproducibility.
- All major analysis, modeling, and validation results in this repository can be reproduced using the included sample files.

---

## 🛠️ Tools & Technologies
- Python (Pandas, NumPy, Scikit-learn)  
- Jupyter / Google Colab  
- Matplotlib / Seaborn  
- Excel  

---

##  Final Takeaway

Anomaly detection can identify irregular patterns in public health data, but **trustworthiness requires validation**.

By combining:
- statistical evidence  
- model agreement  
- real-world interpretation  

we show anomaly detection can be both **effective and interpretable**.

## Final Presentation

To read through our final project PowerPoint, it is available here:

→ `Final Presentation/Big Data Analytics – Final Project PPT.pptx`
