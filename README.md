# 🚀 SpaceX Falcon 9 First Stage Landing Prediction

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Plotly Dash](https://img.shields.io/badge/Plotly_Dash-3F4F75?style=flat&logo=plotly&logoColor=white)](https://dash.plotly.com/)
[![Folium](https://img.shields.io/badge/Folium-77B829?style=flat&logo=python&logoColor=white)](https://python-visualization.github.io/folium/)

An end-to-end Data Science project predicting whether the first stage of the SpaceX Falcon 9 rocket will land successfully. By determining booster recovery probabilities, alternate spaceflight companies can estimate launch costs and make data-driven decisions when bidding against SpaceX.

---

# 📌 Executive Summary

SpaceX advertises Falcon 9 launches at approximately **$62 million**, whereas competitor launch costs typically exceed **$165 million**. The primary driver behind these cost savings is the successful recovery and reuse of the first-stage booster.

This project implements a complete data science workflow—from automated API data ingestion and web scraping to exploratory visual analytics, interactive GIS mapping, dynamic dashboarding, and supervised machine learning classification.

## Key Findings

- **Optimal Payload Range:** Landing success density peaks between **2,000 kg and 4,000 kg**.
- **Orbit Reliability:** Orbits such as **ES-L1, GEO, HEO, and SSO** achieved a **100% landing success rate**, while **LEO, VLEO, and ISS** maintained approximately **80–90%** success.
- **Top Performing Site:** **KSC LC-39A** achieved the highest landing success rate (**76.9%**).
- **Predictive Performance:** Logistic Regression, SVM, Decision Tree, and KNN all achieved **83.33% test accuracy**.

---

# 🛠️ Project Architecture & Pipeline

```
Data Collection
      │
      ▼
Data Wrangling
      │
      ▼
EDA & Analytics
      │
      ▼
Dashboarding & Mapping
      │
      ▼
Machine Learning
```

### Pipeline Overview

| Stage | Techniques |
|--------|------------|
| **Data Collection** | SpaceX REST API, BeautifulSoup |
| **Data Wrangling** | Missing value imputation, Feature Engineering, One-Hot Encoding |
| **EDA** | Seaborn, Matplotlib, SQLite |
| **Visualization** | Folium, Plotly Dash |
| **Machine Learning** | StandardScaler, GridSearchCV, Classification Models |

### Workflow

1. **Data Collection**
   - Extracted launch records using the SpaceX REST API.
   - Scraped historical launch tables from Wikipedia using BeautifulSoup.

2. **Data Wrangling**
   - Normalized nested JSON data.
   - Imputed missing payload mass values.
   - Created the binary target variable `Class`.
   - Generated **83 numerical features** through One-Hot Encoding.

3. **Exploratory Data Analysis**
   - Investigated launch success across launch sites, payloads, orbit types, and years.
   - Performed SQL analysis using SQLite.

4. **Interactive Visual Analytics**
   - **Folium:** Created launch site maps and calculated distances to nearby infrastructure using the Haversine formula.
   - **Plotly Dash:** Developed an interactive dashboard with dropdown filters, payload sliders, pie charts, and scatter plots.

5. **Machine Learning**
   - Standardized features using `StandardScaler`.
   - Performed an 80/20 train-test split.
   - Tuned hyperparameters with **10-fold GridSearchCV**.
   - Evaluated models using confusion matrices and test accuracy.

---

# 📊 Machine Learning Model Comparison

All models were evaluated on an independent test dataset (**n = 18**).

| Model | Best Hyperparameters | Cross Validation | Test Accuracy |
|------|------|:------:|:------:|
| **Logistic Regression** | `C=0.1`, `penalty=l2`, `solver=lbfgs` | **84.82%** | **83.33%** |
| **Support Vector Machine** | `C=1.0`, `gamma=0.0316`, `kernel=sigmoid` | **84.82%** | **83.33%** |
| **K-Nearest Neighbors** | `algorithm=auto`, `n_neighbors=10`, `p=1` | **84.82%** | **83.33%** |
| **Decision Tree** | `criterion=gini`, `max_depth=4`, `splitter=best` | **83.21%** | **83.33%** |

## Confusion Matrix

- ✅ True Positives: **12**
- ✅ True Negatives: **3**
- ❌ False Positives: **3**
- ✅ False Negatives: **0**

---

# 📁 Repository Structure

```text
.
├── 01 spacex-data-collection-api.ipynb
├── 02 webscraping.ipynb
├── 03 spacex-Data wrangling.ipynb
├── 04 eda-sql sqllite.ipynb
├── 05 eda-data-viz.ipynb
├── 06 launch site location.ipynb
├── 07 spacex dash app.py
├── 08 SpaceX Machine Learning Prediction.ipynb
├── Data Science Capstone Project Report.pdf
└── README.md
```

---

# 💻 Installation & Usage

## Clone the Repository

```bash
git clone https://github.com/navya-r-krishna/SpaceX-Falcon-9-first-stage-Landing-Prediction.git

cd SpaceX-Falcon-9-first-stage-Landing-Prediction
```

## Install Dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn folium dash plotly
```

## Run the Dashboard

```bash
python "07 spacex dash app.py"
```
---

# 👤 Author

**Navya R Krishna**
