# Early Detection of Stress and Depression Using Natural Language Processing (NLP)

## 1. Project Overview
This research investigates the potential use of Natural Language Processing (NLP) and machine learning techniques for identifying stress-related patterns in text. The current experimental implementation evaluates binary stress-related text classification using the Dreaddit dataset. Depression-specific detection and clinical validation remain outside the scope of the current experiment and require further research.

**Important:** This project is an academic machine learning experiment, not a clinical diagnostic system. Model predictions must not be used to diagnose stress or depression.

## 2. Dataset

- **Dataset:** Dreaddit
- **Dataset repository used:** `jp-prakash05/dreaddit`
- **Training samples:** 2,838
- **Test samples:** 715
- **Training label distribution:**
  - Label 0: 1,350 samples
  - Label 1: 1,488 samples
- **Task:** Binary classification of stress-related text

The dataset was loaded using the Hugging Face `datasets` library. The original dataset documentation, label definitions, provenance, and license should be checked and cited before final publication.

## 3. Methodology

The experiment follows these steps:

1. Load the dataset.
2. Prepare text and binary labels.
3. Convert text into numerical features using TF-IDF.
4. Use unigram and bigram features.
5. Train Logistic Regression and LinearSVC classifiers.
6. Evaluate both models on the test set.
7. Perform stratified 5-fold cross-validation on the training set.
8. Examine classification errors using a confusion matrix and failure analysis.

The TF-IDF vectorizer uses a maximum of 20,000 features and sublinear term frequency scaling.

## 4. Models

1. **TF-IDF + Logistic Regression**
2. **TF-IDF + LinearSVC**

Both models use the same text feature configuration for comparison.

## 5. Test Results

Results on the independent test set of 715 samples:

| Metric | Logistic Regression | LinearSVC |
|---|---:|---:|
| Accuracy | 0.7217 | 0.7203 |
| Macro Precision | 0.7265 | 0.7207 |
| Macro Recall | 0.7189 | 0.7190 |
| Macro F1-score | 0.7183 | 0.7192 |

The two models achieved similar test performance. Logistic Regression obtained slightly higher accuracy and macro precision, while LinearSVC obtained a slightly higher macro F1-score.

## 6. Five-Fold Cross-Validation

Stratified 5-fold cross-validation was performed on the training set. Results are reported as mean and standard deviation.

| Metric | Logistic Regression | LinearSVC |
|---|---:|---:|
| Accuracy (mean ± SD) | 0.7600 ± 0.0138 | 0.7523 ± 0.0108 |
| Macro Precision (mean ± SD) | 0.7636 ± 0.0159 | 0.7530 ± 0.0118 |
| Macro Recall (mean ± SD) | 0.7566 ± 0.0133 | 0.7502 ± 0.0103 |
| Macro F1 (mean ± SD) | 0.7572 ± 0.0134 | 0.7506 ± 0.0104 |

Logistic Regression achieved higher mean scores across all four cross-validation metrics. The cross-validation results are separate from the independent test results and should not be treated as the same evaluation.

## 7. Confusion Matrix and Failure Analysis

The Logistic Regression model produced the following confusion matrix on the test set:

| Actual / Predicted | Label 0 | Label 1 |
|---|---:|---:|
| Label 0 | 219 | 127 |
| Label 1 | 72 | 297 |

The model correctly classified 516 of 715 test samples and misclassified 199 samples.

Failure analysis should investigate ambiguous text, short responses, contextual language, and possible overlap between the two classes. These are potential explanations and should be verified by examining errors rather than assumed.

![Confusion Matrix](dreaddit_confusion_matrix.png)

## 8. System Architecture

The following diagram illustrates the classification workflow.

![System Architecture](system_architecture.png)

## 9. Survey Analysis

The Google Forms survey received 26 responses. Seventeen participants consented to analysis, and 49 non-empty open-ended answers were extracted from their responses.

The survey is used for exploratory analysis only. It is not used as labelled training data for the Dreaddit classifiers.

Survey data should be handled according to participant consent and applicable privacy requirements. Raw responses should not be published without appropriate permission.

## 10. Repository Contents

The repository includes research analysis materials, model evaluation results, and visualizations. Relevant files include:

- `research_analysis.ipynb` — research analysis notebook
- `model_comparison.csv` — independent test-set model comparison
- `model_5fold_cv_results.csv` — five-fold cross-validation summary
- `dreaddit_confusion_matrix.png` — confusion matrix visualization
- `system_architecture.png` — system architecture diagram
- `final_survey_summary.csv` — aggregate survey summary

File availability may change as the repository is updated.

## 11. Reproducibility

The experiments were conducted in Google Colab using Python and machine learning libraries, including pandas, scikit-learn, Hugging Face datasets, and Matplotlib.

For reproducibility, the final project should record:

- Python version
- Installed package versions
- Dataset source and version
- Random seeds and model parameters
- Instructions for running the notebook

## 12. Limitations

- The dataset and its labels require careful verification against the original documentation.
- The models use traditional TF-IDF features and may not capture context, sarcasm, or complex language.
- The test-set results are moderate and do not establish generalization to all populations or languages.
- The survey is small and is not used as training data.
- Classification performance does not establish clinical validity or the ability to diagnose stress or depression.
- Further testing on appropriately consented, representative data is required.

## 13. Ethics

This project concerns sensitive mental-health-related text. Predictions should not be used to make clinical decisions.

Dataset terms, participant consent, privacy, and potential bias must be considered before sharing data or publishing results. Raw survey responses and raw text from dataset error analysis should not be uploaded publicly unless the applicable consent and license permit it.

## 14. References

Add the original Dreaddit dataset publication, the verified dataset documentation, and relevant peer-reviewed NLP and text classification research here. Verify bibliographic details before submission.
