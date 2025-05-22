# Data Royale DIKE 2023 – Music Genre Multiclass Prediction

**Authors**  
- Bagus Cipta Pratama (23/516539/PA/22097)  
- Hafid Sasayuda Ambardi (23/519841/PA/22308)  
- Joseph Greffen Komala   (23/519909/PA/22318)  

**Affiliation**  
Departemen Ilmu Komputer dan Elektronika,  
Fakultas Matematika dan Ilmu Pengetahuan Alam,  
Universitas Gadjah Mada  

---

## 📖 Project Overview

Data Royale DIKE is a data science competition organized by the Research Cell of the Computer Science & Electronics Department and the Data Science & AI Division of OmahTI. Participants tackle end-to-end challenges—data wrangling, exploratory analysis, feature engineering, and model building—to predict music genres. Entries are evaluated on prediction quality (using pre-defined metrics) and the robustness of methodology, providing hands-on experience in extracting actionable insights from real-world datasets.


---

## 🛠️ Methodology

1. **Exploratory Data Analysis (EDA)**

   * Assessed feature distributions, missing values, outliers, and class imbalance.
   * Dropped non-informative columns (e.g., `artist_name`, dominated `track_name`).
   * Visualized correlations and scatter‐matrix to spot key relationships (e.g., between feature₂–₃, feature₂–₅).

2. **Pre-processing**

   * **Outlier handling**: compared IQR vs. Z-score clipping on `duration` & `popularity`. IQR capping yielded best accuracy (0.933 vs. 0.932).
   * **Missing values**: tested multiple imputation strategies and selected KNN Imputer (k=15) for highest accuracy gain.
   * **Balance**: applied SMOTE + Tomek links to even out class distribution.

3. **Feature Engineering**

   * Engineered new features: sum and ratio of feature₂ & feature₃.
   * Grouped sparse categories for `track_name` and `time_signature` to avoid overfitting.

4. **Model Selection & Tuning**

   * Compared XGBoostClassifier vs. KNN under varying preprocessing pipelines.
   * Evaluated on F1‐score and stability (std dev).
   * Chose **XGBoost** with upsampling-overfit pipeline (accuracy ≈ 85.3%, stable).

---

## 📊 Results & Discussion

* **Best Model**: XGBoost with f1‐score > 0.80.
* **Key Insights**:

  * Feature₄ had the strongest negative correlation with genre class (r ≈ −0.43).
  * Combination of IQR outlier capping and KNN imputation gave the highest lift in predictive performance.
* **Impact**: Automating genre assignment can reduce manual tagging effort and support smarter recommendation engines.

---

## 🎯 Conclusion

Our study demonstrates that a well-tuned XGBoost model, coupled with targeted preprocessing and feature engineering, can achieve robust multiclass music genre classification (> 80% f1-score). This pipeline can be integrated into streaming and music curation platforms to cut costs and improve user experience.
