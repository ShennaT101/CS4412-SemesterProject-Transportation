# Transportation Data Mining (CS 4412 – M2)

## Overview

This project is part of the CS 4412 Data Mining course milestone M2: Initial Implementation. The goal of this milestone is to explore a dataset, perform exploratory data analysis (EDA), preprocess the data, and apply an initial data mining technique to discover patterns.

The dataset contains monthly transportation statistics including safety metrics, freight activity indicators, and transportation service indices. The analysis focuses on identifying patterns in transportation activity and safety outcomes.

---

## Dataset

Dataset: Monthly Transportation Statistics

The dataset includes variables such as:

- Air safety fatalities
- Highway fatality rates
- Rail fatalities
- Transportation Services Index (freight, passenger, combined)
- Truck tonnage index

These variables provide insight into transportation activity and safety trends over time.

---

## Exploratory Data Analysis

Exploratory analysis was performed to understand the dataset structure and relationships between variables.

Key steps included:

- Summary statistics using Pandas
- Correlation analysis between transportation indicators
- Histograms and boxplots to inspect distributions
- Scatter plots to explore relationships between freight activity and transportation metrics

The analysis revealed several moderate correlations among transportation safety indicators and freight activity measures.

---

## Data Preprocessing

Several preprocessing steps were applied before performing clustering:

- Selected numeric features from the dataset
- Removed columns containing only missing values
- Replaced infinite values with NaN
- Imputed missing values using column means
- Standardized features using z-score normalization

Standardization ensures that features with larger numeric ranges do not dominate distance calculations during clustering.

---

## Mining Technique: Clustering

K-Means clustering was applied to identify natural groupings within the transportation data.

Steps performed:

1. Standardized numeric features
2. Applied the elbow method to determine the optimal number of clusters
3. Selected **k = 3 clusters**
4. Visualized clusters using **Principal Component Analysis (PCA)**

---

## Results

The clustering analysis revealed three distinct transportation patterns:

**Cluster 0 – Moderate Transportation Activity**

Represents periods with moderate freight movement and moderate safety metrics. These observations likely correspond to typical operational transportation conditions.

**Cluster 1 – Higher Safety Risk Periods**

Characterized by higher fatality-related indicators but lower freight activity. These periods may correspond to months with unusual transportation incidents or environmental factors affecting safety.

**Cluster 2 – High Transportation Activity**

This cluster shows the highest transportation service indices and truck tonnage values. These observations likely correspond to periods with strong freight and passenger transportation demand.

---

## Repository Structure
.idea

data/
Monthly_Transportation_Statistics.csv

docs/
CS4412_M2_Summary.pdf
M1_Project_Proposal.pdf

notebooks/
M2_analysis.ipynb

README.md


---

## Future Work (M3)

Future work will expand the analysis by applying additional data mining techniques such as:

- Hierarchical clustering
- DBSCAN clustering
- Anomaly detection

These methods will help further investigate unusual transportation patterns and cluster structures.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook
