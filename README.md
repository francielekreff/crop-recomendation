# Crop Recommendation

This repository contains the notebook developed for a Machine Learning project. The goal of this project is to evaluate supervised learning algorithms for automatic crop recommendation based on soil physicochemical attributes and environmental conditions.

## Objective

This work investigates the use of machine learning models to predict the most suitable crop based on seven input features:

- Nitrogen (N)
- Phosphorus (P)
- Potassium (K)
- Temperature
- Humidity
- pH
- Rainfall

The target variable corresponds to the recommended crop, making this a multiclass classification problem.

## Dataset

The project uses the **Crop Recommendation Dataset**, publicly available on Kaggle.

The dataset contains:

- 2,200 instances
- 7 numerical features
- 22 crop classes
- 100 samples per class
- No missing values

The crop classes include, among others, rice, maize, coffee, cotton, banana, apple, grapes, mango, watermelon, and chickpea.

## Methodology

The experimental workflow was organized into the following steps:

1. Exploratory Data Analysis (EDA)
2. Preprocessing
3. Stratified train-test split
4. Algorithm spot-checking
5. Hyperparameter optimization with nested cross-validation
6. Final model training
7. Evaluation on the test set
8. Model interpretability analysis

## Data Split

The dataset was split using a stratified holdout approach:

- 80% for model development
- 20% for final evaluation

The test set was kept isolated during model selection and hyperparameter optimization.

## Evaluated Algorithms

During the spot-checking stage, five supervised learning algorithms were evaluated:

- K-Nearest Neighbors (KNN)
- Gaussian Naive Bayes
- Support Vector Machine (SVM)
- Random Forest
- Gradient Boosting

The initial comparison was performed using 5-fold stratified cross-validation with the default hyperparameters from scikit-learn.

## Hyperparameter Optimization

After spot-checking, the three best-performing models were selected for hyperparameter optimization using nested cross-validation.

Nested cross-validation was used to separate:

- The hyperparameter selection process, performed in the inner loop
- The performance estimation process, performed in the outer loop

After comparing the candidate models, the best-performing algorithm was tuned again using the full development set to define the final hyperparameters.

## Evaluation Metrics

The following metrics were used:

- Accuracy
- Weighted precision
- Weighted recall
- Weighted F1-score
- Confusion matrix

The weighted F1-score was used as the main metric for model comparison.

## Main Results

The final model achieved high predictive performance on the test set, with few classification errors.

| Metric | Value |
|---|---:|
| Accuracy | 0.9955 |
| Weighted precision | 0.9959 |
| Weighted recall | 0.9955 |
| Weighted F1-score | 0.9954 |

## Reproducibility

The experiments were developed in Python using Google Colab. The main libraries used were:

- pandas
- NumPy
- matplotlib
- seaborn
- scikit-learn
- umap-learn

To support reproducibility, a fixed random seed (`42`) was used in steps involving randomness, including the train-test split, cross-validation procedures, and stochastic models.

## How to Run

1. Open the notebook in Google Colab or in a local Jupyter environment.
2. Load the `Crop_recommendation.csv` dataset.
3. Run the notebook cells in order.
4. Check the generated outputs for:
   - Exploratory Data Analysis
   - Initial model comparison
   - Nested cross-validation
   - Final evaluation
   - Interpretability analysis
