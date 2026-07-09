# Papilledema Classification with Radiomic Features

Patient-level, radiomics-based binary classification of **papilledema vs. normal** optic discs. Originally developed as a final course project (Artificial Intelligence, Üsküdar University).

## Summary

Papilledema is bilateral optic disc swelling caused by elevated intracranial pressure; distinguishing it from pseudopapilledema is clinically difficult and normally relies on expert interpretation. This project builds a machine-learning classifier from **746 radiomic features** extracted from the optic disc, using a dataset of **966 samples from 69 subjects** (48 normal, 21 papilledema).

Key methodology:

- **Patient-level cross-validation** — `GroupShuffleSplit` (10 outer repeats) + `StratifiedGroupKFold` (5 inner folds) to prevent leakage between samples from the same patient
- **Preprocessing** — median imputation, low-variance filtering, Pearson-correlation pruning, `RobustScaler` normalization
- **Feature selection** — MRMR (Minimum Redundancy Maximum Relevance)
- **Models** — Logistic Regression, RBF-kernel SVM, Random Forest, ExtraTrees, Gradient Boosting, KNN, plus a calibrated soft-voting ensemble, all tuned with Optuna (TPE sampler)
- **Calibration** — sigmoid (Platt) calibration with F1-maximizing threshold selection
- **Explainability** — SHAP feature-importance analysis
- **Statistics** — Friedman test across models, Wilcoxon pairwise tests with Bonferroni correction

### Results

Mean performance across 10 outer cross-validation repeats:

| Model | Macro-F1 (mean ± std) | ROC AUC (mean ± std) |
|---|---|---|
| ExtraTrees | 0.847 ± 0.060 | 0.943 ± 0.062 |
| Ensemble (soft voting) | 0.847 ± 0.066 | 0.940 ± 0.065 |
| Random Forest | 0.846 ± 0.065 | 0.937 ± 0.067 |
| SVM (RBF) | 0.839 ± 0.070 | 0.922 ± 0.065 |
| Gradient Boosting | 0.822 ± 0.136 | 0.918 ± 0.075 |
| KNN | 0.818 ± 0.079 | 0.906 ± 0.075 |
| Logistic Regression | 0.787 ± 0.097 | 0.887 ± 0.081 |

ExtraTrees, the soft-voting ensemble, and Random Forest are effectively tied for the best mean macro-F1; the SVM produced the single best individual repeat (macro-F1 = 0.951). A Friedman test found a statistically significant difference across models (χ² = 15.83, p = 0.0147). Full methodology, figures, and discussion are in [`report/final_report.md`](report/final_report.md) / [`report/final_report.pdf`](report/final_report.pdf).

## Project structure

```
.
├── notebooks/radiomics_pipeline.ipynb   # end-to-end pipeline notebook
├── src/                                 # pipeline modules (preprocessing, feature
│                                         # selection, models, calibration, SHAP, stats)
├── scripts/                             # CLI entry points (run_pipeline, run_shap,
│                                         # report/notebook generation, smoke test)
├── tests/                               # unit tests for src/
├── results/                             # figures, metric tables, run manifest
├── report/                              # final report (md / html / pdf / docx)
└── assets/                              # pipeline diagram
```

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

## Quick smoke test

```bash
python scripts/smoke_test.py
```

## Full pipeline run

```bash
python scripts/run_pipeline.py
```

## Notebook

```bash
jupyter notebook notebooks/radiomics_pipeline.ipynb
```
