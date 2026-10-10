# Regime-Conditional Conformal Reserve Intelligence (RCCRI)

Reproducible implementation of RCCRI: uncertainty-conditioned reserve management and dispatch commitment for renewable-integrated microgrids, combining ExtraTrees forecasting, conformalized quantile regression with regime-conditional (Mondrian) calibration, a bounded reserve and graduated commitment policy, and LIME / DiCE explainability.

## Contents

| Path | Description |
|---|---|
| `RCCRI_R1_Revision_Notebook.ipynb` | Current notebook. Reproduces every table and figure of the manuscript under a strict chronological protocol (primary) and a random exchangeable protocol (reference): point-forecast and uncertainty-quantification baselines, the commitment-policy ablation (spread-based, width-based and conformal lower-bound commitments), the 60-day system-level dispatch simulation with deterministic, robust and two-stage stochastic rolling-horizon LP baselines, seasonal windows with day-block bootstrap confidence intervals, Pareto and sensitivity analyses, adaptive conformal inference, LIME fidelity metrics and DiCE counterfactual case studies. |
| `Outputs_R1/tables/` | All result tables of the current notebook (JSON / CSV). |
| `Outputs_R1/figures/` | All figures of the current notebook (PNG). |
| `RCCRI_Notebook.ipynb`, `Outputs/` | Original notebook and its outputs (random-split protocol only), kept for reference. |

## Data

The notebook uses the public *Renewable Energy and Weather Conditions* dataset (196,776 fifteen-minute records, 2017–2022), available on Kaggle (`samanemami/renewable-energy-and-weather-conditions`). Place the CSV at `MyDrive/Datasets/Energy/Renewable.csv` (Google Colab) or edit `DATASET_PATH` in the first code cell.

## Running

Open the notebook in Google Colab and run the cells in order (about 45 minutes on a standard CPU runtime; the LP baselines dominate). All outputs are written to the Colab local disk under `/content/RCCRI_R1_outputs`; an optional final cell copies the tables and figures to Google Drive.

Dependencies: `scikit-learn`, `lightgbm`, `xgboost`, `torch`, `scipy`, `lime`, `dice-ml`, `pandas`, `matplotlib`, `seaborn`.
