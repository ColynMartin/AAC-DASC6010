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

--- OR

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

## Repository Structure

📌 Workflow:
Sampling → Cleaning → EDA → Feature Engineering → Modeling → Validation → Interpretation

---

## ▶️ How to Reproduce This Project

1. Generate sample dataset  
2. Clean dataset  
3. Create features  
4. Run models  
5. Validate results  
6. Review interpretation  

All required files are included.

---

## 🛠️ Tools & Technologies
- Python (Pandas, NumPy, Scikit-learn)  
- Jupyter / Google Colab  
- Matplotlib / Seaborn  
- Excel  

---

## 📌 Final Takeaway

Anomaly detection can identify irregular patterns in public health data — but **trustworthiness requires validation**.

By combining:
- statistical evidence  
- model agreement  
- real-world interpretation  

we show anomaly detection can be both **effective and interpretable**.
