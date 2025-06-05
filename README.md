# CalorieExpenditureAnalysis
Participated in a Kaggle Playground Series that uses synthetic data to apply different aspects of machine learning and data science. 

# Calories Burned Prediction — Kaggle Competition
## Overview

Competition: Kaggle Calories Burned Prediction (www.kaggle.com/competitions/playground-series-s5e5/overview/)
Goal: Predict how many calories were burned during a workout.
Evaluation metric: RMSLE, which penalizes underestimates more than overestimates and is more sensitive to small prediction errors on lower calorie values.
Features:
- Gender (categorical)
- Age, Height, Weight, Duration, Heart_Rate, Body_Temp (numerical)
- Calories (target)

## Tools & Libraries
- Python
- pandas, NumPy
- scikit-learn
- seaborn, matplotlib
- Kaggle Notebooks

## Preprocessing
- No missing values found
- Checked and visualized feature and target distributions
- One-hot encoded Gender → Renamed sex_female → sex for consistency
- Dropped id column
- Applied log transform on Calories to normalize skewness

## Exploratory Data Analysis

- Age, Body_Temp, and Calories were **right-skewed**
- Weight showed signs of a **bimodal** distribution
- Most other features were unimodal or uniform
- Weak linear correlation with target, but Random Forest captured non-linear patterns well

## Modeling
- Linear Regression → RMSLE: ~0.179
- Random Forest Regressor → RMSLE: ~0.060
- Selected Random Forest due to its lower error and strong generalization without needing intense tuning.

## Evaluation
- Used 80/20 train/validation split
- Evaluation metric: RMSLE
- Final predictions made on test set using Random Forest model
- Inverse log-transform applied using `np.expm1()`
- Final predictions rounded to 1 decimal for consistency with training data

## Submission Format
- Format: id,Calories
- File: my_submission.csv
- Generated directly in Kaggle notebook and submitted from output

## Citation 
@misc{playground-series-s5e5,
    author = {Walter Reade and Elizabeth Park},
    title = {Predict Calorie Expenditure},
    year = {2025},
    howpublished = {\url{https://kaggle.com/competitions/playground-series-s5e5}},
    note = {Kaggle}
}

