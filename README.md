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
