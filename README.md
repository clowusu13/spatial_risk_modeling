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

## Project structure
- src/: reusable code
- notebooks/: exploratory and reporting notebooks
- configs/: YAML configs for parameters
- data/: ignored (not committed)
- outputs/: ignored (not committed)

## How to run
Coming soon.
