# Pattern Discovery in U.S. Transportation Systems  
**CS 4412 – Data Mining (M4 Final Deliverable)**  
**Author:** Shenna Tawiah  
**Date:** May 2026  

---

## 📌 Project Overview

This project applies a complete data mining pipeline to the **Monthly Transportation Statistics dataset** to uncover patterns in transportation activity and safety outcomes across multiple modes.

The goal is to identify meaningful transportation system profiles and understand how activity relates to risk.

This final (M4) version expands on earlier work by adding:
- Cluster validation and tradeoff analysis  
- Temporal pattern analysis  
- Interpretable modeling (Decision Trees)  
- Critical assessment of limitations and validity  

---

## 🎯 Discovery Questions

1. Do distinct transportation system profiles emerge?  
2. How does activity relate to safety outcomes?  
3. Which variables drive these differences?  
4. Are patterns structural or influenced by time?  

---

## 📊 Dataset

- **Source:** Monthly Transportation Statistics  
- **Location:** `data/Monthly_Transportation_Statistics.csv`  
- **Scope:** Multi-modal (rail, aviation, freight, highway)  
- ~950 observations, 100+ features  

---

## ⚙️ Methodology

### 🔹 Preprocessing
- Removed sparse features (<50% coverage)  
- Replaced infinite values  
- Mean imputation  
- Z-score normalization  

### 🔹 Modeling Pipeline
- K-Means clustering  
- Silhouette analysis for cluster selection  
- PCA for visualization  
- Decision Tree for interpretation  
- Temporal analysis  
- Stability validation (multiple seeds)  
- DBSCAN (alternative clustering)  

---

## 📈 Key Results

### 🔹 Cluster Selection Tradeoff

| k | Silhouette Score |
|--|------------------|
| 3 | ~0.33 |
| 7 | ~0.51 |

👉 Final choice: **k = 3**  
- Lower score  
- Much higher interpretability  

---

### 🔹 Cluster Profiles

| Cluster | Description |
|--------|------------|
| **0** | Elevated risk, moderate activity |
| **1** | High activity, lower risk |
| **2** | Moderate / transitional |

---

### 🔹 Key Insight

> High transportation activity does **not necessarily** lead to higher fatality rates.

This suggests that modern systems can achieve **high efficiency while maintaining safety**.

---

### 🔹 Temporal Finding

Cluster membership shows **clear time structure**:

- Earlier years → higher-risk systems  
- Later years → lower-risk, more efficient systems  

👉 Indicates long-term improvement in transportation systems  

---

### 🔹 Decision Tree Insight

- Primary split: ~76 rail fatalities  
- Secondary split: aviation fatalities  

👉 Safety variables dominate cluster formation  

---

## 🔍 Validation

- K-Means run across multiple seeds  
- Consistent silhouette scores  

👉 Results are **stable and reproducible**

---

## 🔄 Alternative Method

- DBSCAN tested  
- Did not produce meaningful clusters  

👉 K-Means is more appropriate for this dataset  

---

## ⚠️ Critical Assessment

### Validity
- Supported by PCA separation and stability testing  
- No ground truth labels  

### Limitations
- Missing data required imputation  
- K-Means assumptions (spherical clusters)  
- Feature selection sensitivity  

### Temporal Confounding
- Patterns partially driven by time  

### Ethics
- Results are correlational, not causal  

---

## 📁 Project Structure


```
.
│
├── data/
│ └── Monthly_Transportation_Statistics.csv
│
├── docs/
│ ├── CS4412_M2_Summary.pdf
│ ├── CS4412_M3CompleteImplementation.pdf
│ ├── CS4412_M4_FinalDeliverable_*.pdf
│ └── M1_Project_Proposal.pdf
│
├── figures/
│ ├── pca_plot.png
│ └── tree.png
│
├── images/ # (duplicate visuals / optional use)
│ └── pca_plot.png
│
├── notebooks/
│ ├── M2_Analysis.ipynb
│ ├── M3_CompleteImplementation.ipynb
│ └── M4_FinalDeliverable.ipynb
│
├── report/
│ └── img.png
│
├── README.md
```

---

## 🚀 How to Run

### 1. Open project
```bash
git clone <your-repo>
cd CS4412PROJECT

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

## Final Takeaway
This project shows that:
- Transportation systems form distinct profiles
- Efficiency and safety can coexist
- Patterns reflect both structure and historical evolution
---

## 🔮 Future Work (M4)
- Tune DBSCAN / alternative clustering
- Add time-series modeling
- Expand feature engineering
- Incorporate external validation datasets 

---

## 👤 Author
**Shenna Tawiah**  
CS 4412 – Data Mining