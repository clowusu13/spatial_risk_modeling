# Spatial Risk Modeling

Geospatial data science project comparing statistical and machine learning approaches using spatial cross-validation.

## Goals
- Build a reproducible pipeline: data prep -> features -> spatial CV -> model training -> evaluation -> interpretability -> maps
- Compare methods fairly under spatial cross-validation

## Methods (planned)
- Logistic regression (baseline)
- Spatial lag / autocovariate logistic
- Gradient boosting (LightGBM or XGBoost)
- Bayesian spatial model (PyMC)

## Evaluation
- Spatially blocked cross-validation (GroupKFold)
- ROC-AUC, PR-AUC, balanced accuracy
- Calibration and threshold-based metrics

## Current status
- Notebook 01 (`notebooks/01_build_modeling_dataset.ipynb`) builds the modeling table (`data/processed/model_table.csv`) from the raw wells table using consistent cleaning rules (pH sanity checks, depth, one-row-per-location, and dropping rows missing core predictors/target).
- Notebook 02 (`notebooks/02_spatial_cv_and_baseline.ipynb`) sets up spatially blocked cross-validation and runs baseline model comparisons.

Raw data stays local under `data/` and is not committed.

## Early findings (baseline run)
Baseline results using features: pH, depth, and geology unit (one-hot). Metrics are computed from out-of-fold predictions under spatially blocked CV. Coordinates were geomasked for privacy in the shared version, please treat results as illustration only.

Logistic regression (class_weight=balanced):
- ROC-AUC: ~0.65
- PR-AUC: ~0.15
- Best balanced accuracy: ~0.64 (best threshold ~0.50)
- n=990, positives=78 (~7.9%)

LightGBM (initial parameters and scale_pos_weight):
- Under the same blocked CV, LightGBM performed worse than the logistic baseline on ROC/PR metrics in the first pass.

Next steps to improving the ML comparison fairly includes hyperparameter tuning, handling rare geology categories, and adding spatial lag features.

## Project structure
- src/: reusable code
- notebooks/: exploratory and reporting notebooks
- configs/: YAML configs for parameters
- data/: ignored (not committed)
- outputs/: ignored (not committed)

## How to run
Coming soon.
