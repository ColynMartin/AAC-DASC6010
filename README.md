# AAC-DASC6010 (title work in progress)

Goal: This project evaluates how anomaly detection models can be applied to large-scale public health surveillance data. Using the CDC COVID-19 Case Surveillance Public Use Data, we analyze reporting patterns over time to identify unusual observations that deviate from expected trends.

The primary goal is not just to detect anomalies, but to determine whether these anomalies are meaningful, interpretable, and trustworthy in real-world public health contexts.


Objectives: 

~ Apply anomaly detection models to COVID-19 surveillance data

~ Compare outputs across multiple models

~ Evaluate whether detected anomalies are valid and explainable

~ Ensure results align with the underlying dataset


Dataset:
Source: CDC COVID-19 Case Surveillance Public Use Data
Link to Download:
Original dataset size: ~14GB
Workflow Adaptation

The original plan was to perform analysis on the full dataset. However, due to its size, direct processing and modeling were not computationally feasible.

To address this, the workflow was adapted to use a representative sampled dataset:

A 0.5% sample was generated using chunk-based processing
The sample was validated to preserve:
demographic distributions
outcome variables
temporal trends

All analysis, modeling, and validation were conducted using this sampled dataset to ensure:

efficiency
reproducibility
consistency

#WEEKLY WORKUP BREAKDOWN: (MAYBE OR WILL BE INCLUDED AS PLAN)

Week 1 – Data Acquisition & Preparation

~ Generated representative sample dataset
~ Cleaned missing and inconsistent values
~ Standardized formats and variables

Week 2 – Feature Engineering & EDA

~ Created derived features:
daily case counts

rolling averages

normalized case rates

~ Conducted exploratory data analysis

Week 3 – Anomaly Detection Modeling

~ Implemented:
Isolation Forest

Local Outlier Factor (LOF)

One-Class SVM

Detected and compared anomalies across models

Week 4 – Validation & Interpretation

Verified anomalies correspond to actual data points

Ensured consistency with the dataset

Interpreted anomalies using real-world context:

reporting delays

backlog updates

outbreak spikes

Week 5 – Synthesis & Presentation

Summarized findings

Evaluated hypotheses

Prepared final presentation
