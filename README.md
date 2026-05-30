# 🌧️ Rainfall Prediction in Melbourne Using Machine Learning
### End-to-end ML pipeline · Random Forest vs Logistic Regression · ~84% Accuracy · Production-ready design

![Python](https://img.shields.io/badge/Python-3.8+-blue?style=flat-square&logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-latest-F7931E?style=flat-square&logo=scikitlearn)
![Accuracy](https://img.shields.io/badge/Test_Accuracy-~84%25-green?style=flat-square)
![Dataset](https://img.shields.io/badge/Dataset-BOM_Australia_2008--2017-lightblue?style=flat-square)
![License](https://img.shields.io/badge/License-Educational-lightgrey?style=flat-square)

> Predicts daily rainfall occurrence in Melbourne using historical meteorological data — with rigorous data leakage prevention, seasonal feature engineering, and a deployable Scikit-learn pipeline achieving **~84% accuracy**.

---

## 🎯 Why This Problem Is Hard

Rainfall prediction isn't a clean Kaggle exercise. Real meteorological data comes with missing values, class imbalance, geographic variability, and — critically — **data leakage risk** from how the target variable is defined. This project addresses all of these explicitly.

---

## 📊 Results

| Model | Accuracy | Recall (Rain Events) |
|-------|----------|---------------------|
| Random Forest | ~84% | Good overall |
| Logistic Regression | ~84% | **Better** — superior minority class recall |

**Key insight:** In rainfall prediction, missing an actual rain event (false negative) costs more than a false alarm. Logistic Regression's higher recall for the minority class makes it the preferred model for operational use — accuracy alone doesn't tell the full story.

**Most influential features:** Humidity-related variables and engineered seasonal features.

---

## 🔍 Key Engineering Decisions

### 1. Data Leakage Prevention
Redefined the prediction target to avoid using same-day rainfall measurements as input features — one of the most common production ML mistakes that inflates test accuracy but fails in deployment.

### 2. Seasonal Feature Engineering
Extracted cyclical seasonal signals from raw date fields — capturing weather patterns (wet/dry seasons) that the raw numerical features don't expose directly.

### 3. Geographic Filtering
Restricted analysis to geographically close locations (Melbourne, Melbourne Airport, Watsonia) to reduce variability from unrelated climate zones in the national dataset.

### 4. Deployable Pipelines
Built Scikit-learn Pipelines combining preprocessing + model in a single serializable object — not just notebook-style step-by-step code.

---

## 🗂 Dataset

| Property | Value |
|----------|-------|
| Source | Australian Bureau of Meteorology (BOM) + Kaggle Rattle Package |
| Coverage | Australia, 2008–2017 |
| Target Locations | Melbourne · Melbourne Airport · Watsonia |
| Task | Binary classification — Rain tomorrow: Yes / No |

---

## 🧩 Modeling Approach

### Random Forest Classifier
- Robust to feature interactions and non-linear relationships
- Hyperparameter tuning via GridSearchCV
- Feature importance analysis — identifies humidity and seasonal features as top predictors

### Logistic Regression
- Interpretable baseline — clear coefficient attribution
- Better recall on minority class (actual rain days)
- Preferred model for operational rainfall prediction

Both models trained via unified preprocessing + modeling pipeline.


---

## 📐 Evaluation Suite

- Accuracy, Precision, Recall, F1-score
- Confusion Matrix — explicit false negative analysis
- Feature Importance (Random Forest)
- Model comparison on same train/test split — fair benchmarking

---

## ⚙️ Tech Stack

| Tool | Purpose |
|------|---------|
| Python | Core language |
| Pandas + NumPy | Data cleaning, feature engineering |
| Scikit-learn | Pipelines, GridSearchCV, models, evaluation |
| Matplotlib + Seaborn | EDA and results visualization |

---

## 🚀 Getting Started

```bash
# Clone the repository
git clone https://github.com/amarskdev/rainfall-prediction-melbourne.git
cd rainfall-prediction-melbourne

# Install dependencies
pip install -r requirements.txt

# Run the notebook
jupyter notebook rainfall_prediction_melbourne.ipynb
```

---

## 📁 Project Structure

```
rainfall-prediction-melbourne/
│
├── rainfall_prediction_melbourne.ipynb   # Full pipeline: EDA → features → models → evaluation
├── requirements.txt                      # Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn
└── README.md
```

---

## 🔭 Roadmap

- [ ] XGBoost / LightGBM comparison
- [ ] SMOTE for class imbalance handling
- [ ] Time-series cross-validation (prevent temporal leakage)
- [ ] Probability calibration for confidence-aware predictions
- [ ] FastAPI deployment for real-time inference

---

*Built with production ML principles — leakage prevention, deployable pipelines, and metric selection driven by real-world cost of errors.*

---

## 🤝 Connect With Me


<div align="center">

### 👤 About the Author

**Amar Kumar**  
*Senior Backend Engineer · IBM Certified AI Engineer*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-amarskdev-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/amarskdev)
[![GitHub](https://img.shields.io/badge/GitHub-amarskdev-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/amarskdev)
[![Gmail](https://img.shields.io/badge/Gmail-amarsk.dev-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:amarsk.dev@gmail.com)
[![LeetCode](https://img.shields.io/badge/LeetCode-amarskdev-FFA116?style=for-the-badge&logo=leetcode&logoColor=white)](https://leetcode.com/u/amarskdev)
[![Instagram](https://img.shields.io/badge/Instagram-amarsk.dev-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/amarsk.dev/)
[![Credly](https://img.shields.io/badge/Credly-Badges-FF6B00?style=for-the-badge&logo=credly&logoColor=white)](https://www.credly.com/users/amarskdev/)

*If you found this project useful, consider giving it a ⭐ — it means a lot!*

</div>



