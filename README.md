# 🌍 Global AQI Exploratory Data Analysis

<div align="center">

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.7+-11557c?style=for-the-badge&logo=python&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-0.12+-4c72b0?style=for-the-badge&logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**A comprehensive Exploratory Data Analysis of global Air Quality Index (AQI) data across 16,000+ locations worldwide.**

[📓 View Notebook](#-notebook-structure) · [📊 Key Findings](#-key-findings) · [🚀 Getting Started](#-getting-started) · [📁 Dataset](#-dataset)

</div>

---

## 📌 Project Overview

Air pollution is one of the leading environmental health threats globally. This project performs a deep, structured EDA on a dataset of **16,695 global location records**, analyzing overall AQI and four individual pollutant sub-indices — **CO, Ozone, NO₂, and PM2.5** — alongside geographic coordinates.

The analysis follows the **UBM Rule**:
- **U** — Univariate Analysis
- **B** — Bivariate Analysis
- **M** — Multivariate Analysis

> **Business Objective:** Provide data-driven insights to support environmental agencies, policymakers, and public health organizations in identifying the most polluted regions and the dominant pollutants driving poor air quality worldwide.

---

## 📁 Dataset

| Property | Details |
|---|---|
| **File** | `AQI-and-Lat-Long-of-Countries.csv` |
| **Records** | 16,695 rows |
| **Features** | 7 columns |
| **Missing Values** | None |
| **Duplicates** | None |

### Columns

| Column | Type | Description |
|---|---|---|
| `AQI Value` | int | Overall Air Quality Index (higher = worse) |
| `CO AQI Value` | int | Carbon Monoxide sub-index |
| `Ozone AQI Value` | int | Ozone (O₃) sub-index |
| `NO2 AQI Value` | int | Nitrogen Dioxide sub-index |
| `PM2.5 AQI Value` | int | Fine Particulate Matter sub-index |
| `lat` | float | Latitude of the location |
| `lng` | float | Longitude of the location |

### AQI Category Breakpoints (US EPA Standard)

| AQI Range | Category | Health Concern |
|---|---|---|
| 0 – 50 | 🟢 Good | Little or no risk |
| 51 – 100 | 🟡 Moderate | Acceptable; some risk for sensitive groups |
| 101 – 150 | 🟠 Unhealthy for Sensitive Groups | Sensitive individuals may experience effects |
| 151 – 200 | 🔴 Unhealthy | Everyone may experience health effects |
| 201 – 300 | 🟣 Very Unhealthy | Health alert — serious effects for everyone |
| 301 – 500 | ⚫ Hazardous | Emergency conditions |

---

## 📊 Key Findings

1. **PM2.5 is the dominant driver of AQI** — with a near-perfect Pearson correlation of **r = 0.98** with overall AQI. Fine particulate matter is the single most critical pollutant to regulate.

2. **Most locations have acceptable air quality** — ~46% are *Good* and ~42% are *Moderate*, meaning ~89% of monitored locations fall within the safe range.

3. **Extreme pollution is real and persistent** — Hazardous-zone locations are not anomalies; their AQI values are consistently high, indicating structural industrial or geographic causes.

4. **Northern Hemisphere is significantly more polluted** — Median AQI in the Northern Hemisphere is substantially higher, driven by South Asia, East Asia, and parts of the Middle East and Africa.

5. **CO and NO₂ share combustion sources** — Moderate correlation (r ≈ 0.40) suggests vehicle emission policies address both simultaneously.

6. **Ozone is an independent pollutant** — Weak and even slightly negative correlation with NO₂ (r = −0.25), indicating separate photochemical drivers that need distinct policy responses.

---

## 📓 Notebook Structure

The Jupyter notebook (`AQI_EDA_Analysis.ipynb`) is organized into **6 structured sections** with **20 charts**:

```
AQI_EDA_Analysis.ipynb
│
├── 1. Know Your Data
│   ├── Library Imports
│   ├── Dataset Loading & First View
│   ├── Shape, Info, Dtypes
│   ├── Duplicate Check
│   └── Missing Value Heatmap
│
├── 2. Understanding Your Variables
│   ├── Column Descriptions
│   ├── Statistical Summary (describe)
│   └── Unique Value Counts
│
├── 3. Data Wrangling
│   ├── AQI_Category (EPA classification)
│   ├── Hemisphere (Northern / Southern)
│   ├── Dominant_Pollutant (per location)
│   └── AQI_Severity (min-max normalized)
│
├── 4. Data Visualization (20 Charts)
│   ├── 📊 Univariate (Charts 1–5)
│   │   ├── AQI Histogram + KDE
│   │   ├── AQI Category Bar Chart
│   │   ├── Pollutant Boxplots
│   │   ├── Dominant Pollutant Pie Chart
│   │   └── Overlapping KDE — all pollutants
│   │
│   ├── 📊 Bivariate (Charts 6–10)
│   │   ├── PM2.5 vs AQI Scatter + Regression
│   │   ├── AQI by Hemisphere (Boxplot)
│   │   ├── Correlation Heatmap
│   │   ├── AQI Category vs Dominant Pollutant (Stacked Bar)
│   │   └── Latitude vs AQI Scatter (Category Colored)
│   │
│   └── 📊 Multivariate (Charts 11–20)
│       ├── Global AQI Map (Lat/Lng scatter)
│       ├── Violin Plot by AQI Category
│       ├── Grouped Bar — Pollutants × Category
│       ├── Binned Lat×Lng Heatmap
│       ├── Pairplot (sampled, hue=Category)
│       ├── CDF by AQI Category
│       ├── Outlier Detection (Z-Score)
│       ├── PM2.5 KDE by Hemisphere
│       ├── 2×2 Scatter — Each Pollutant vs AQI
│       └── Horizontal Stacked Bar — Category by Dominant Pollutant
│
├── 5. Solution to Business Objective
│   └── Key Findings Summary Table + Recommendations
│
└── 6. Conclusion & Next Steps
```

---

## 🚀 Getting Started

### Prerequisites

```bash
Python >= 3.10
```

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/aqi-eda-analysis.git
cd aqi-eda-analysis

# Install dependencies
pip install -r requirements.txt
```

### Run the Notebook

```bash
jupyter notebook AQI_EDA_Analysis.ipynb
```

Or open directly in **Google Colab**:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

> ⚠️ Make sure `AQI-and-Lat-Long-of-Countries.csv` is in the same directory as the notebook, or update the file path in the *Dataset Loading* cell.

---

## 🛠️ Tech Stack

| Library | Purpose |
|---|---|
| `pandas` | Data loading, wrangling, feature engineering |
| `numpy` | Numerical computations, Z-score |
| `matplotlib` | Core plotting engine |
| `seaborn` | Statistical visualizations (heatmap, violin, pairplot) |
| `scipy.stats` | Statistical tests, Z-score outlier detection |

### `requirements.txt`

```
pandas>=2.0
numpy>=1.24
matplotlib>=3.7
seaborn>=0.12
scipy>=1.10
jupyter>=1.0
```

---

## 📂 Repository Structure

```
aqi-eda-analysis/
│
├── AQI_EDA_Analysis.ipynb          # Main EDA notebook (20 charts)
├── AQI-and-Lat-Long-of-Countries.csv  # Dataset
├── requirements.txt                # Python dependencies
└── README.md                       # This file
```

---

## 💡 Business Recommendations

| Priority | Action | Expected Impact |
|---|---|---|
| 🔴 High | Implement strict PM2.5 emission standards in South/East Asia | Reduces AQI for the most polluted zones globally |
| 🔴 High | Place Hazardous-AQI locations on emergency monitoring programs | Early warning + faster intervention |
| 🟠 Medium | Strengthen vehicle emission regulations to target CO + NO₂ together | Dual-pollutant reduction from single policy |
| 🟠 Medium | Develop separate Ozone reduction strategies (photochemical drivers) | Ozone doesn't respond to combustion controls |
| 🟡 Low | Expand AQI monitoring in Southern Hemisphere | Better data coverage for currently under-monitored regions |

---

## 🔮 Next Steps

- [ ] **Predictive Modeling** — Train a regression model to predict AQI from pollutant sub-indices and geographic features
- [ ] **Clustering** — Use K-Means or DBSCAN to identify geographic pollution clusters
- [ ] **Time Series** — Incorporate temporal AQI data to study seasonal patterns
- [ ] **Interactive Dashboard** — Build a Plotly/Dash or Streamlit app for real-time exploration
- [ ] **Country-level Aggregation** — Reverse-geocode lat/lng to add country and city labels

---

## 🤝 Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-analysis`)
3. Commit your changes (`git commit -m 'Add new analysis'`)
4. Push to the branch (`git push origin feature/new-analysis`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Your Name**
- GitHub: https://github.com/tomararpit147
- LinkedIn: https://linkedin.com/in/arpittomar05

---

<div align="center">

⭐ **If you found this project useful, please give it a star!** ⭐

*Made with ❤️ and lots of data*

</div>
