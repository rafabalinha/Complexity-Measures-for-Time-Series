# Complexity Measures for Time Series

This repository contains the code and experimental outputs developed for a study on the relationship between time series complexity and forecasting model performance. The project investigates whether the **Complexity Estimate** of a time series is associated with forecasting difficulty, measured through the predictive errors obtained by different forecasting models. It also analyses forecasting models performance on an instance space.

The work was developed in the context of the 2025/2026 second-semester internship/project unit at the Faculty of Sciences, University of Porto.

## Project Overview

The main objective of this project is to analyse how time series complexity influences forecasting errors. The study focuses primarily on the **Complexity Estimate (CE)**.

In addition to CE, other complexity-related features are used to construct an instance space and to support the interpretation of forecasting performance across different regions of the feature space.

The empirical analysis uses monthly time series and compares the performance of several forecasting approaches, including baselines, ARIMA models, and machine learning models.

## Repository Structure

The repository is organised as follows:

```text
.
├── data_selection_and_ARIMA_implementation/
│   ├── data_selection_and_ARIMA_implementation.ipynb
│   ├── final_df.csv
│   ├── cv_df_cv.csv
│   ├── acf_pacf_stationarity/
│   ├── acf_pacf_stationary/
│   └── plots_forecasts_arima/
│
├── random_Forest_and_LightGBM_implementation/
│   ├── random_Forest_and_LightGBM_implementation.ipynb
│   ├── final_df.csv
│   ├── forecasts_df.csv
│   ├── params_rf_df.csv
│   └── params_lgbm_df.csv
│
├── instance_space_analysis/
│   ├── instance_space_analysis.ipynb
│   ├── complexity_pairplot.png
│   ├── correlation_matrix.png
│   ├── instance_space_features.png
│   ├── instance_space_model_performance.png
│   ├── pca_component_matrix.png
│   ├── pca_loadings.png
│   └── scree_plot.png
│
├── statistical_testing/
│   ├── complexity_estimate_statistical_testing.ipynb
│   ├── boxplot_nmae_by_complexity.png
│   ├── boxplot_nrmse_by_complexity.png
│   ├── boxplot_smape_by_complexity.png
│   ├── heatmap_spearman.png
│   └── nemenyi_heatmaps.png
│
├── README.md
└── LICENSE
```

## Methodological Summary

The project follows four main stages:

1. **Data selection and statistical forecasting**
   A subset of time series is selected according to the Complexity Estimate distribution. Baseline methods and ARIMA-based forecasting models are evaluated, and diagnostic plots are generated.

2. **Machine learning forecasting models**
   Random Forest and LightGBM models are implemented and evaluated using lag-based supervised learning representations of the time series.

4. **Statistical testing**
   The relationship between Complexity Estimate and forecasting performance is analysed using correlation measures and statistical comparison procedures across complexity groups.

4. **Instance space analysis**
   A set of complexity-related time series features is extracted and projected into a two-dimensional instance space using dimensionality reduction. This representation is used to analyse whether different regions of the feature space are associated with different forecasting behaviours.
   
## Forecasting Models

The forecasting models considered in this project include:

* Naive forecasting;
* Seasonal naive forecasting;
* AutoARIMA;
* Random Forest;
* LightGBM.

Model performance is evaluated using the following error metrics:

* Symmetric Mean Absolute Percentage Error (SMAPE);
* Normalised Mean Absolute Error (NMAE);
* Normalised Root Mean Squared Error (NRMSE).

## Complexity and Feature Analysis

The analysis includes the Complexity Estimate as the main complexity measure. Additional time series features are used to characterise the series and construct the instance space. These features support the analysis of whether forecasting errors and model dominance patterns vary across different regions of the time series feature space.

## Requirements

The notebooks were developed in Python and require the standard scientific Python ecosystem. The main dependencies include:

```text
re
os
random
joblib
datasetsforecast
utilsforecast
window_ops
numpy
pandas
scipy
scikit-learn
matplotlib
seaborn
statsmodels
statsforecast
mlforecast
lightgbm
functools
itertools
math
optuna
antropy
ordpy
scikit-posthocs
jupyter
```

A virtual environment is recommended before running the notebooks.

Example installation:

```bash
python -m venv .venv
source .venv/bin/activate
pip install re os random joblib datasetsforecast utilsforecast window_ops numpy pandas scipy scikit-learn matplotlib seaborn statsmodels statsforecast mlforecast lightgbm functools itertools math optuna antropy ordpy scikit-posthocs jupyter
```

Alternatively, if using Anaconda:

```bash
conda create -n time-series-complexity python=3.11
conda activate time-series-complexity
pip install re os random joblib datasetsforecast utilsforecast window_ops numpy pandas scipy scikit-learn matplotlib seaborn statsmodels statsforecast mlforecast lightgbm functools itertools math optuna antropy ordpy scikit-posthocs jupyter
```

## Usage

The notebooks should be executed in the following order:

1. `data_selection_and_ARIMA_implementation/data_selection_and_ARIMA_implementation.ipynb`
2. `random_Forest_and_LightGBM_implementation/random_Forest_and_LightGBM_implementation.ipynb`
3. `instance_space_analysis/instance_space_analysis.ipynb`
4. `statistical_testing/complexity_estimate_statistical_testing.ipynb`

To start Jupyter Notebook:

```bash
jupyter notebook
```

or, alternatively:

```bash
jupyter lab
```

Some notebooks depend on intermediate CSV files generated in previous stages. The repository includes several generated outputs to support reproducibility and inspection of the reported results.

## Data

This project uses monthly time series data for empirical forecasting analysis. The original raw dataset, M4 Competition, is not included in this repository.

Generated intermediate files and figures are included to document the experimental workflow and the results obtained during the project.

## Reproducibility Notes

The results may depend on the versions of the Python packages used, as well as on stochastic elements in machine learning models and hyperparameter optimisation procedures. For more reproducible execution, users are encouraged to set random seeds where applicable and to document the exact package versions used in their environment.

## License

This project is distributed under the terms of the **GNU General Public License v3.0**. See the `LICENSE` file for the full license text.

## Author

Rafael Balinha
Faculty of Sciences, University of Porto
