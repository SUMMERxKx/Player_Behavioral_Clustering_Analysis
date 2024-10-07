# Bustabit Player Clustering Project

## Overview

This project aims to analyze and cluster player behavior based on data from the Bustabit game platform. The goal is to group players into distinct behavioral clusters by processing game data, applying feature engineering, and leveraging machine learning techniques. This analysis can provide insights into player strategies, such as identifying "Risk-takers," "Conservative players," and "Balanced players."

## Project Pipeline

The pipeline includes the following steps:

1. **Data Preprocessing**
   - Load the dataset and handle missing values (NaN).
   - Convert date columns to datetime format for easier manipulation.
   - Replace missing values in key columns like `CashedOut` with a default value.
   - Handle infinite values resulting from division operations by replacing them with NaN.

2. **Feature Engineering**
   - Aggregate player data to generate useful features such as:
     - Average bet size
     - Cash-out statistics
     - Risk tolerance (calculated as the ratio of standard deviation to mean of cash-out values)
     - Win rate (profit vs. total bet amount)
   - Handle remaining NaN values by using a mean imputation strategy.

3. **Exploratory Data Analysis (EDA)**
   - Perform correlation analysis to understand relationships between different features.
   - Generate visualizations like correlation heatmaps to assist in understanding data trends.

4. **Feature Scaling**
   - Standardize the feature set using `StandardScaler` to ensure all features contribute equally during the clustering process.

5. **Dimensionality Reduction with PCA**
   - Apply Principal Component Analysis (PCA) to reduce dimensionality and remove noise, while retaining most of the important information.

6. **KMeans Clustering**
   - Use the KMeans algorithm to group players into distinct clusters.
   - Employ the "Elbow Method" to determine the optimal number of clusters for the data.

7. **Cluster Analysis**
   - Analyze and interpret the characteristics of each cluster.
   - Visualize clusters based on important features like average bet size and cash-out behavior.

8. **Player Type Assignment**
   - Assign meaningful labels to each cluster, such as "Risk-takers," "Conservative players," and "Balanced players."
   - Save the results to a CSV file for further analysis.

## Requirements

To run this project, you will need the following libraries installed:

- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`
- `seaborn`

You can install these dependencies via pip:

```bash
pip install pandas numpy scikit-learn matplotlib seaborn
