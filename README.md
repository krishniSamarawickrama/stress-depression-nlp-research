# Stress and Depression Detection Using NLP

## Project Overview
This repository contains exploratory survey analysis and
an emotion-classification experiment using TF-IDF with
Logistic Regression and Linear Support Vector Machine (SVM).

**Important:** The public emotion dataset used in the current
experiment is not a stress/depression-specific dataset.
Its results must not be interpreted as clinical or
stress/depression detection performance.

## Current Dataset
- Dataset: dair-ai/emotion
- Training samples: 16,000
- Validation samples: 2,000
- Test samples: 2,000
- Task: Emotion classification

## Models
1. TF-IDF + Logistic Regression (baseline)
2. TF-IDF + Linear SVM (comparison)

## Test Results

| Metric | Logistic Regression | Linear SVM |
|---|---:|---:|
| Accuracy | 0.8325 | 0.8800 |
| Macro Precision | 0.8692 | 0.8401 |
| Macro Recall | 0.6880 | 0.8027 |
| Macro F1-score | 0.7375 | 0.8196 |

## 5-Fold Cross-Validation

| Metric | Logistic Regression | Linear SVM |
|---|---:|---:|
| Accuracy (mean ± SD) | 0.8032 ± 0.0092 | 0.8834 ± 0.0061 |
| Macro Precision (mean ± SD) | 0.8512 ± 0.0116 | 0.8666 ± 0.0089 |
| Macro Recall (mean ± SD) | 0.6495 ± 0.0125 | 0.8261 ± 0.0132 |
| Macro F1 (mean ± SD) | 0.7016 ± 0.0140 | 0.8442 ± 0.0105 |

## Survey Analysis
The Google Forms survey received 26 responses.
Seventeen participants consented to analysis, and 49
non-empty open-ended answers were extracted.
This small survey is used for exploratory analysis only;
it is not used as labelled training data for the classifier.

## Reproducibility
The experiment was conducted in Google Colab using Python,
pandas, scikit-learn, Hugging Face datasets, and Matplotlib.
The exact installed package versions and training notebook
should be recorded before the experiment is considered
fully reproducible.

## Limitations
- The current emotion dataset does not provide stress/depression-specific labels.
- Survey responses are limited in size.
- Emotion classification performance does not establish
  clinical validity or mental-health diagnostic ability.

## Ethics
Survey data should only be shared in accordance with
participant consent and applicable privacy requirements.
