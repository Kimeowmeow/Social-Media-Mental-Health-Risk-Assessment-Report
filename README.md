# Social Media Mental Health Risk Assessment

## 📌 Project Overview

This project aims to assess the risk of anxiety and depression among social media users based on their usage patterns and self-reported psychological indicators. We apply machine learning and clustering algorithms to identify high-risk user groups and analyze the relationship between digital behavior and mental health.

## 🎯 Objectives

1. Predict users at risk of anxiety and depression using machine learning models.
2. Use clustering algorithms to detect groups with the highest risk.
3. Discover key behavioral and demographic predictors.
4. Provide actionable risk signals and early intervention suggestions.

## 🧠 Dataset

We used the **[Social Media and Mental Health Dataset](https://www.kaggle.com/datasets/souvikahmed071/social-media-and-mental-health)** from Kaggle. It contains 451 user responses with the following features:

* **Demographics**: Age, Gender, Relationship Status, Occupation, Affiliated Organization
* **Usage Behavior**: Platforms used, Time spent, Distraction levels, Restlessness
* **Psychological Symptoms**: Depression, Anxiety, ADHD-related symptoms, Self-esteem indicators

## ⚙️ Methodology

### 1. Data Preprocessing

* Handled missing values
* Renamed long column names for better clarity
* Encoded categorical variables using Label Encoding / One-Hot Encoding
* Converted social media usage time to numerical values (in hours)
* Calculated number of platforms used per respondent

### 2. Feature Engineering & Risk Indicator Construction

Four composite risk indicators were created:

* `ADHD_Risk`: based on purposeless use, distractions, difficulty concentrating
* `Anxiety_Risk`: based on restlessness and being bothered by worries
* `Depression_Risk`: based on depressive feelings, sleep issues, and fluctuating interest
* `Self_Esteem_Risk`: based on validation seeking and social comparison

A binary risk label was defined using the **75th percentile as the threshold**.

### 3. Predictive Modeling

Two classifiers were trained using Random Forest:

* **Anxiety Model**

  * AUC: 1.000 (Perfect prediction)
  * Top predictor: `Restlessness`
* **Depression Model**

  * AUC: 0.767
  * Top predictor: `Social_Comparison`

### 4. Clustering Analysis

* **K-Means** clustering was used to segment users into four groups.
* **Cluster 0** was identified as the **group with the highest risk**.
* Characteristics of Cluster 0:

  * Average age: 22.45
  * Daily usage: 4.69 hours
  * Platform count: 5.47
  * High levels of anxiety, depression, and ADHD risk indicators

### 5. Visualization

* Risk distribution plotted by age, usage time, and clusters
* Heatmaps to show average risk levels per cluster
* Dimensionality reduction using PCA for visualizing group spread

## 🔍 Key Findings

* Social media restlessness and comparison behavior are strong predictors of mental health risk
* Users under 25 years old with high usage time and multiple platforms are more vulnerable
* Machine learning effectively separates high and low-risk individuals
* K-Means clustering clearly highlights a specific high-risk group needing intervention

## 💡 Clinical Implications

* Early detection tools can be built based on digital behavior
* Risk stratification allows resource prioritization for mental health services
* Personalized interventions (e.g., reducing usage time, mindfulness) can be guided by model outputs
