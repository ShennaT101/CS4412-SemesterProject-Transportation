# 🚦 Transportation Pattern Discovery (K-Means + PCA)

## 📌 Overview
This project implements a complete data mining pipeline on the **Monthly Transportation Statistics dataset** to uncover patterns in transportation activity and safety outcomes across multiple modes, including aviation, rail, and freight systems.

The workflow combines:
- Data preprocessing and feature selection  
- Feature scaling (standardization)  
- K-Means clustering  
- PCA for visualization  
- Decision Tree classification for interpretability  

---

## ⚠️ Dataset Note
The original proposal (M1) referenced an automobile sales dataset. This project was updated in M2 to use the **Monthly Transportation Statistics dataset**, which better supports multi-modal transportation analysis.

---

## ⚙️ Methodology

### Data Preprocessing
- Removed Index column
- Dropped sparse features (<50% non-null)
- Replaced infinite values with NaN
- Applied mean imputation

### Clustering
- K-Means clustering
- Evaluated using Elbow Method + Silhouette Score

### Dimensionality Reduction
- PCA for visualization

### Interpretation
- Cluster centroids analyzed
- Decision Tree used for feature importance

---

## 📊 Key Results

### Silhouette Scores
| k | Score |
|--|------|
| 2 | 0.483 |
| 3 | 0.396 |
| 4 | 0.423 |
| 5 | 0.473 |
| 6 | 0.489 |
| 7 | **0.510** |
| 8 | 0.495 |
| 9 | 0.495 |

- Best numerical separation: **k=7**
- Final model used: **k=3 (interpretability)**

---

## 🧠 Cluster Insights

### Cluster 0 — High Activity, High Risk
- Highest fatalities  
- High freight movement  

### Cluster 1 — High Activity, Lower Risk
- Highest overall activity  
- Lower fatalities  

### Cluster 2 — Moderate Activity
- Balanced system behavior  

---

## 📈 Visualization
- PCA confirms clear cluster separation  
- See: `images/pca_plot.png`

---

## 📁 Project Structure

```
.
├── data/
│   └── Monthly_Transportation_Statistics_20260308.csv
│
├── docs/
│   ├── M1_Project_Proposal.pdf
│   ├── CS4412_M2_Summary.pdf
│   └── CS4412_M3CompleteImplementation_Tawiah_Shenna.pdf
│
├── images/
│   └── pca_plot.png
│
├── notebooks/
│   ├── M2_Analysis.ipynb
│   └── M3_CompleteImplementation.ipynb
│
├── report/
│
└── README.md
```

---

## 🚀 How to Run

### Install dependencies
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### Run notebook
```bash
jupyter notebook notebooks/M3_CompleteImplementation.ipynb
```

---

## ⚖️ Key Insight
Although **k=7 achieved the highest silhouette score**,  
**k=3 was selected** to balance interpretability and meaningful cluster definitions.

---

## ⚠️ Limitations
- Loss of data from dropping sparse columns  
- K-Means assumptions (spherical clusters)  
- PCA reduces interpretability  
- Mean imputation may introduce bias  

---

## 🔮 Future Work (M4)
- Improve feature engineering  
- Add deeper statistical validation  
- Expand real-world implications  

---

## 👤 Author
**Shenna Tawiah**  
CS 4412 – Data Mining