# Malawi-Flood-Prediction
This project is done as part of the UNICEF Arm 2030 Vision #1: Flood Prediction in Malawi competition hosted on Zindi, an African data science competition hosting platform.

## Dataset

Each row of the original dataset corresponds to a Square, which is an area in Southern Malawi. Each square has the following data:
- 17 weeks of rainfall data prior to the floods
- elevation
- land type
- flooding percentage (target variable)

## Supplementary datasets used

For a more in-depth exploratory data analysis and to generate more features, I made use of the following datasets:
- polygons of administrative regions in Malawi (https://data.humdata.org/dataset/malawi-administrative-level-0-3-boundaries)
- polygons of water bodies in Africa (https://energydata.info/dataset/africa-water-bodies-2015)

## Exploratory Data Analysis

The first EDA notebook documents the relationships between the given features (rainfall, elevation, land type and flooding percentage).

The second EDA notebook aggregates Squares into Level 3 administrative regions and looks into the rainfall, elevation and flooding characteristics in each administrative region. 

## Feature engineering

On top of engineering features from the original dataset, I derived more features for each Square to help with the prediction:
- aggregated rainfall data
- relative amount of rainfall (compared with mean rainfall in the administrative region)
- relative elevation (compared with mean elevation in the administrative region)
- number of water bodies in the same administrative region
- distance to closest water body

## Modelling

I experimented with several regression techniques and the results are as follows:

| Model | Lasso  | Ridge  | Random Forest | Lightgbm | Multi-Layer-Perceptron |
| :---: | :-:    | :-:    | :-:           | :-:      | :-:                    |
| RMSE  | 0.2183 | 0.2183 | 0.1226        | 0.1167   | 0.0964                 |
