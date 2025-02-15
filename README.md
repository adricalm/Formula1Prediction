<!-- PROJECT LOGO -->
<p align="center">
  <a href="https://github.com/joelcalm/Formula1Prediction">
    <img src="f1logo.png" alt="Logo" width="150" height="40">
  </a>
</p>  

# Formula1 Outcome Prediction

This project showcases the implementation and evaluation of machine learning algorithms, including XGBoost, Random Forest, SVM, and Logistic Regression, for predicting Formula 1 race outcomes of the 2020-2024 seasons, such as race winners and finishing groups (podium, points, no-points), using historical data from 1950 to the end of the 2024 season.

---

## About The Project

This repository contains code and analysis for predicting Formula 1 race outcomes. The project’s core objective is to forecast the race winner and classify drivers into three performance groups—podium (top 3), points (4–10), and no-points (>10)—across multiple seasons (2020–2024).

The prediction tasks face unique constraints, such as only one winner per race and limited podium spots, making conventional metrics insufficient. Custom evaluation strategies were developed, including "race-wise accuracy," to ensure predictions adhere to real-world constraints. The project also explored the potential of regression-based approaches (predicting continuous finishing positions) and converting those predictions into groups.

### Approach and Methodology

- **Data Integration:** Historical data from Kaggle’s Formula 1 dataset (1950–2020) complemented with additional scraped data from the Ergast API for the 2021–2024 seasons.
- **Feature Engineering:** Incorporation of driver age, DNF rates, constructor reliability, home-race flags, and recent performance metrics to capture nuanced factors impacting results.
- **Modeling:** Evaluation of multiple models including Logistic Regression, Random Forest, SVM, and XGBoost. Both classification and regression strategies were employed.
- **Metrics:** Custom race-wise accuracy for winner prediction, group accuracy, F1 scores, and ROC/AUC for assessing classification of podium, points, and no-points groups.
- **Temporal Cross-Validation:** TimeSeriesSplit was used to ensure future races are predicted using only historical data.

This workflow led to significant improvements in accuracy after feature engineering, hyperparameter tuning, and feature selection. XGBoost emerged as the top performer for both winner and group predictions.

### Built With

- [Scikit-Learn](https://scikit-learn.org/)
- [XGBoost](https://xgboost.readthedocs.io/)
- [Numpy](https://numpy.org/)
- [Pandas](https://pandas.pydata.org/)
- [Matplotlib](https://matplotlib.org/)
- [Seaborn](https://seaborn.pydata.org/)

---

## Getting Started

### Data Sources

- **Kaggle F1 Dataset (1950–2020)**  
  Used as the base historical dataset containing race results, drivers, constructors, and qualifying sessions.

- **Ergast API (2021–2024)**  
  Additional data was scraped to update the dataset and include recent races up to 2024.

## Usage

### Comprehensive Workflow in a Single Notebook:
- **Data Preprocessing:** Merging datasets, cleaning missing values, and engineering features.
- **Model Training:** Implementing and training multiple models (Logistic Regression, Random Forest, SVM, XGBoost).
- **Model Evaluation:** Assessing performance with race-wise accuracy, group accuracy, and F1 scores.
- **Visualization:** Creating correlation matrices, ROC curves, and confusion matrices.
- **Betting Strategy:** Simulating predictive betting analysis and comparing returns to actual outcomes.

### Results and Performance

After feature engineering and hyperparameter tuning:

- **Winner Prediction:** XGBoost improved race-wise accuracy from **~0.46** to **~0.66**.
- **Group Classification:** Significant improvements in correctly identifying podium, points, and no-points finishers.
- **Model Insights:** Grid position, reliability metrics, and recent performance were among the most influential features.
