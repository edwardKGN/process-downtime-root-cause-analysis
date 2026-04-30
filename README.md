# Process Downtime Root Cause Analysis

## Overview
This project models an process downtime

Using XGBoost

Variations in production times creates chaos in production planning and has led to missing production throughput targets.

By optimizing the process which shows significant spread, companies can:
- Improve consistency of production throughput
- Enable next stage of optimization to reduce the downtime of each production
- Minimize process overruns

## Features
- The problem is formulated as a feature importance problem.

XGBoost is use to iteratively regress features that lead to downtime spread by:
- Randomly Generating Forest Trees
- Calculate the Feature Importance from Gain

## Tech Stack
- Python
- NumPy / Pandas
- XGBoost
- Data Visualization (Matplotlib)

## Input Data
- process_step_downtime.csv

Synthetic sample data is provided in the /data folder.

## How to Run
- Run 00_Process Step Downtime Spread Analysis.ipynb
- Run 01_Process Step Feature.ipynb

## Example Use Case
The system accepts inputs from production steps downtime and generates synthetic step specific process data for demonstration of analytics 

## Results / Screenshots

Here is the result of the analysis

![DistDowntime](screenshots/downtime_distribution.png)

![CorrMat](screenshots/correlation_matrix.png)

- Based on Histogram data from Downtime spread, it was found that there was insufficient samples to get a statistically signficant distribution
- Based on Correlation Matrix, current features used were found to have minimal correlation with Downtime. This may indicate that there may be other factors affecting the downtime.

Due to limitations from the downtime distribution and correlation matrix, the following ranking and SHAP plot (plotted for completion sake) can be ignored.

![FeatureRank](screenshots/feature_importance_ranking.png)

![Shapley](screenshots/shap_plot.png)

## Next Actions
- Increase Number of Samples to improve Extropolation Capability
- Seek for more features to map against

## Future Improvements
- Gather more sample data of the process
- Expand search for more features that may affect the downtime spread

## Lessons Learned
- Application of XGBoost and Feature Importance
