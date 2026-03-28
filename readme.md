# Urban Traffic Pattern Mining

## Overview
This project performs unsupervised traffic pattern discovery on the METR-LA 
dataset using time-based feature engineering, DBSCAN/HDBSCAN clustering, and 
PCA visualization to identify recurring congestion patterns and anomalous 
traffic behaviour.

## Dataset
METR-LA Traffic Dataset - Speed readings from 207 loop detectors on Los 
Angeles County highways, collected over 4 months (March 2012 - June 2012) 
at 5-minute intervals.

Source: https://github.com/liyaguang/DCRNN

## Execution Order
Run notebooks in this order:
1. `01_data_understanding_preprocessing.ipynb` - Load, explore, clean data
2. `02_feature_engineering.ipynb` - Extract temporal traffic features
3. `03_unsupervised_modelling.ipynb` - DBSCAN/HDBSCAN clustering
4. `04_visualization_analysis.ipynb` - Visualize patterns and clusters
5. `05_interpretation_ethics.ipynb` - Interpret findings, ethics discussion

## Environment
- Python 3.9.18
- See requirements.txt for all dependencies

## How to Run
```bash
pip install -r requirements.txt
cd notebooks
jupyter notebook