# A Developer-Centred Evaluation of False Positive Impact in ML-Based Intrusion Detection Systems

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Dataset: UNSW-NB15](https://img.shields.io/badge/Dataset-UNSW--NB15-brightgreen)](https://research.unsw.edu.au/projects/unsw-nb15-dataset)

> **Blekinge Institute of Technology (BTH)** — Master's Thesis Project  
> **Authors:** Sai Akhil Gouravarapu & Sri Aditya Gundimeda  

---

## Abstract

Machine Learning (ML) based Intrusion Detection Systems (IDS) achieve high classification performance on standard benchmarks. However, limited research evaluates how high false positive rates (FPR) impact software developers during post-deployment maintenance. This study presents a **two-phase mixed-method evaluation**:
1. **Technical Assessment:** Evaluates Logistic Regression and Random Forest models on the **UNSW-NB15 dataset**.
2. **Human-Centred Assessment:** Investigates how varying false positive scenarios (Low, Medium, High threshold conditions) influence developer trust, alert clarity, and system adoption among 15 software developers.

---

## Key Findings

- **Random Forest Outperformed Baseline:** Achieved **87.05% Accuracy**, **98.62% Recall**, and reduced false negatives from 3,115 to 626 compared to Logistic Regression (83.55% accuracy).
- **False Positives Drive Loss of Trust:** The **Impact of False Positives** construct scored the highest mean (4.17 / 5.00), demonstrating that high FPR significantly reduces reliance and increases assessment overhead.
- **Alert Clarity vs. Decision Support:** While developers found alerts easy to understand (4.33 / 5.00), direct decision support scored lower (3.60 / 5.00), indicating a need for contextual threat intelligence (mitigations, severity, trends).

---

## Model Performance Summary

| Metric | Logistic Regression (Baseline) | Random Forest (Primary) | Difference |
| :--- | :---: | :---: | :---: |
| **Accuracy** | 83.55% | **87.05%** | +3.50 pp |
| **Precision** | 80.19% | **81.66%** | +1.47 pp |
| **Recall** | 93.13% | **98.62%** | +5.49 pp |
| **F1-Score** | 86.18% | **89.34%** | +3.16 pp |
| **False Positive Rate** | 28.19% | **27.14%** | -1.05 pp |
| **False Positives (FP)** | 10,429 | **10,040** | -389 |
| **False Negatives (FN)** | 3,115 | **626** | -2,489 |

---

## False Positive Threshold Scenarios

Classification threshold tuning on the Random Forest model was used to simulate operational conditions for developer testing:

| Scenario | Classification Threshold | False Positive Rate | Focus / Description |
| :--- | :---: | :---: | :--- |
| **Low FP Condition** | 0.70 | Low | High confidence; fewer alerts, lower false alarms |
| **Medium FP Condition** | 0.50 | 27.14% | Default balanced operational baseline |
| **High FP Condition** | 0.30 | 38.28% | Sensitive detection; high threat coverage, excessive false alarms |

---

## Developer Survey Constructs ($n=15$)

| Construct | Question Range | Mean Score (1–5 Scale) |
| :--- | :---: | :---: |
| **Trust in IDS Alerts** | Q1–Q3 | **4.07** |
| **Impact of False Positives** | Q4–Q7 | **4.17** |
| **Alert Usefulness & Clarity** | Q8–Q11 | **3.85** |
| **Adoption & Acceptance** | Q12–Q14 | **3.82** |

---

## Repository Structure

```text
ml-ids-developer-trust/
├── data/
│   ├── raw/                      # Instructions / location for UNSW-NB15 files
│   └── processed/                # Preprocessed feature arrays
├── notebooks/
│   └── ml_ids_false_positive_experiment.ipynb # Full pipeline & ML execution
├── survey/
│   ├── survey_instrument.pdf     # Questionnaire structure
│   └── responses_anonymized.xlsx # Anonymized developer survey results
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
