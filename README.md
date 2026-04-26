# 🔍 UPI Fraud Detection — Exploratory Data Analysis

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange?logo=jupyter)
![Status](https://img.shields.io/badge/Status-EDA%20Complete-green)
![Domain](https://img.shields.io/badge/Domain-FinTech%20%7C%20Fraud%20Detection-purple)

> An end-to-end Exploratory Data Analysis on UPI (Unified Payments Interface) transaction data to uncover fraud patterns — and document why pattern learning is infeasible with this dataset.

---

## 📌 Project Overview

This project performs a thorough EDA on a UPI transaction dataset labelled with a `fraud_flag` (1 = Fraud, 0 = Genuine). The goal was to understand the data, identify fraud signals, and assess whether a machine learning model could be built on top.

**Key Outcome:** After rigorous statistical and visual analysis, **no meaningful difference** was found between fraudulent and genuine transactions across any feature — a critical finding that is fully documented in this project.

---

## 📁 Project Structure

```
upi-fraud-detection/
│
├── data/
│   └── upi_fraud.csv          ← Raw dataset (not tracked in git)
│
├── notebooks/
│   └── 01.eda.ipynb           ← Main EDA notebook
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## 📊 What's Inside the Notebook

| Section | Description |
|---|---|
| **1. Setup & Data Loading** | Library imports, dataset loading, shape check |
| **2. Basic Data Inspection** | Column info, dtypes, statistical summary |
| **3. Missing Values & Duplicates** | Data quality check with visuals |
| **4. Target Variable Analysis** | Class balance — bar + pie chart |
| **5. Amount Analysis** | Distributions, KDE, boxplots, Mann-Whitney U test |
| **6. Categorical Feature Analysis** | Fraud rate per category, stacked bars, Chi-square tests |
| **7. Time-Based Analysis** | Hourly fraud patterns, weekend vs weekday |
| **8. Geographic Analysis** | State-wise fraud count and rate |
| **9. Correlation Analysis** | Heatmap, feature-target correlations, violin plots |
| **10. Key Findings & Conclusion** | Summary table, root cause, next steps |

---

## 🔑 Key Findings

- 📉 **Amount distributions** of fraud and genuine transactions are nearly identical
- 🏷️ **Categorical features** (device type, network, transaction type) show uniform fraud rates
- 🕐 **Time of day** — fraud follows transaction volume, no suspicious hour clusters
- 🗺️ **Geography** — fraud count correlates with state size, not elevated fraud rate
- 📊 **Chi-square & Mann-Whitney tests** confirm no statistically significant differences

> ⚠️ **Conclusion:** The dataset exhibits near-zero feature separability, making standard supervised ML models ineffective. This finding itself is the project's most important contribution.

---

## 🛠️ Technologies Used

- **Python 3.10+**
- **Pandas** — Data manipulation
- **NumPy** — Numerical operations
- **Matplotlib & Seaborn** — Visualisations
- **SciPy** — Statistical tests (Mann-Whitney U, Chi-square)
- **Jupyter Notebook** — Interactive analysis

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/Ishwarimankari/upi-fraud-detection.git
cd upi-fraud-detection
```

### 2. Create a virtual environment
```bash
python -m venv venv
venv\Scripts\activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Add the dataset
Place `upi_fraud.csv` inside the `data/` folder.

### 5. Run the notebook
```bash
jupyter notebook notebooks/01.eda.ipynb
```

---

## 🔮 Potential Next Steps

- **Graph-based fraud detection** — Model transaction networks
- **Anomaly detection** — Isolation Forest, Autoencoders (unsupervised)
- **Richer dataset** — Include session-level, behavioral, or device-fingerprint data
- **Feature engineering** — Velocity, behavioral sequences, device fingerprinting

---

## 👤 Author

**Ishwari Mankari**
- GitHub: [@Ishwarimankari](https://github.com/Ishwarimankari)

---

## 📄 License

This project is open-source under the [MIT License](LICENSE).
