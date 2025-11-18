# 🌲 Forest Cover Type Prediction – Capstone Project

This repository contains my **Capstone Project** on predicting **forest cover type** using classical machine learning models.

Given cartographic features (elevation, soil type, wilderness area, distances, etc.), the goal is to classify each 30m × 30m land plot into one of **seven forest cover types**.

---

## 📌 Problem Statement

> Build and evaluate machine learning models that can accurately predict the **Forest Cover Type** (7 classes) from cartographic variables using the Forest Cover Type dataset (UCI / Kaggle).

Target classes (Cover_Type: 1–7):

1. Spruce/Fir  
2. Lodgepole Pine  
3. Ponderosa Pine  
4. Cottonwood/Willow  
5. Aspen  
6. Douglas-fir  
7. Krummholz  

---

## 📂 Dataset Overview

- **Dataset name:** Forest Cover Type  
- **Rows:** ~581,000  
- **Columns:** 54 features + 1 target  
- **Type:** Multiclass classification  

### 🔹 Feature Types

- **Numerical features (10)**  
  - Elevation  
  - Aspect  
  - Slope  
  - Horizontal/Vertical distance to hydrology  
  - Horizontal distance to roadways  
  - Horizontal distance to fire points  
  - Hillshade indices (9am, noon, 3pm)  

- **Categorical (binary) features (44)**  
  - **Wilderness_Area1–4** (one-hot)  
  - **Soil_Type1–40** (one-hot)  

### 🎯 Target

- `Cover_Type` – integer from **1 to 7** representing the forest cover type.

---

## 🧠 Methods & Models

The notebook walks through the full ML pipeline:

1. **Exploratory Data Analysis (EDA)**  
   - Shape, data types, missing values  
   - Summary statistics  
   - Class distribution  
   - Correlation analysis  

2. **Data Preprocessing**
   - Feature understanding (numeric vs. one-hot features)
   - Train–test split

3. **Baseline Models (Untuned)**
   - Logistic Regression  
   - K-Nearest Neighbors (KNN)  
   - Decision Tree Classifier  
   - Random Forest Classifier  
   - Extra Trees Classifier  
   - AdaBoost Classifier  
   - Gradient Boosting Classifier  

4. **Model Evaluation**
   - Accuracy score  
   - Classification report  
   - Comparison “scorecard” for all models  

5. **Model Tuning (GridSearchCV / Hyperparameters)**
   - Tuned **Extra Trees Classifier**  
   - Tuned **Decision Tree Classifier**  
   - Tuned **KNN Classifier**  

6. **Final Scorecard & Conclusions**
   - Compare **untuned vs tuned** models  
   - Choose best-performing model  

---

## 🔄 Project Flow (High-Level)

1. **Load dataset**  
2. **Perform EDA**  
3. **Preprocess data (train–test split, basic checks)**  
4. **Train multiple baseline models**  
5. **Evaluate and compare all baseline models**  
6. **Tune selected models with GridSearchCV**  
7. **Re-evaluate tuned models**  
8. **Select final model & document insights**

### 📊 Flowchart (for README)

You can keep this **Mermaid** diagram in your README (GitHub renders it):

```mermaid
flowchart TD
    A[Load Dataset] --> B[Exploratory Data Analysis]
    B --> C[Data Preprocessing]
    C --> D[Train-Test Split]
    D --> E[Train Baseline Models\nRF, LR, DT, KNN, AdaBoost, ExtraTrees, GB]
    E --> F[Evaluate & Compare Models\nScorecard]
    F --> G[Hyperparameter Tuning\nGridSearchCV for ET, DT, KNN]
    G --> H[Evaluate Tuned Models]
    H --> I[Select Best Model\n(Tuned Extra Trees)]
    I --> J[Insights & Conclusion]
