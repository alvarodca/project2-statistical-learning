# House Price Prediction Using Supervised Learning

## Objective
The goal of this project is to train various supervised learning models to predict house price categories based on different attributes. Additionally, it focuses on interpreting predictions and identifying the best-performing model.

## Dataset
- **Source**: [Kaggle - House Prices](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data?select=test.csv)
- **Details**: 
  - 1460 observations
  - 81 features
- **Preprocessing**:
  - Training/testing split: 80%/20%.
  - Detailed feature descriptions provided in the Kaggle dataset.

## Data Preprocessing
1. **Handling Missing Values**:
   - Removed columns with excessive missing values.
   - Imputed numerical values using the median.
   - Replaced categorical missing values with "None" or used KNN-based imputation.
2. **Normalization**:
   - Normalized features due to non-normal distributions.
3. **Outlier Detection**:
   - Used DBSCAN, Isolation Forest, and OCSVM. Points identified by at least two methods were removed.
4. **Feature Selection**:
   - Applied Recursive Feature Elimination with Random Forests to reduce features from 81 to 25 (14 numerical, 9 categorical).
5. **Encoding**:
   - Label encoding for ordinal categories (e.g., "Very Good", "Good").
   - Target encoding with cross-validation for other categorical variables.
6. **Categorization**:
   - Divided house prices into five categories using quantiles for classification tasks.

## Models
The following algorithms were implemented and evaluated:

1. **Decision Tree**:
   - Simple baseline model.
   - Accuracy: 57%.

2. **K-Nearest Neighbors**:
   - Optimal `k` = 6.
   - Accuracy: 66%.

3. **Discriminant Analysis**:
   - Linear and Quadratic Discriminant Analysis.
   - Regularized QDA achieved 70% accuracy.

4. **Naive Bayes**:
   - Accuracy: 65%.
   - Limitations due to normality assumptions.

5. **Logistic Regression**:
   - Multinomial and Ordinal regression.
   - Accuracy: 70% (Multinomial), 73% (Ordinal).

6. **Support Vector Machine (SVM)**:
   - Linear and Kernel SVM with Gaussian RBF.
   - Accuracy: 73%.

7. **Random Forest**:
   - Accuracy: 69%.

8. **Gradient Boosting**:
   - XGBoost and alternative libraries.
   - Accuracy: 70% for classification; regression-based approach yielded 74%.

## Final Model
- **Ensemble**:
  - Combined Kernel SVM, Regularized QDA, and XGBoost.
  - Predictions averaged across models for reduced variance.
  - Accuracy: 73% (cross-validation), 72% (test set).

- **Interpretability**:
  - SHAP values were used for feature importance and local interpretability.
  - Key features include quality and area-related attributes.

## Results
- The ensemble classifier performed robustly with an AUC demonstrating strong predictive ability.
- Challenges remained in accurately classifying middle price categories.

## Conclusions
1. Comprehensive preprocessing and feature engineering were critical for effective model training.
2. Combining multiple algorithms improved prediction robustness.
3. Emphasis was placed on both prediction accuracy and interpretability of results.

## Acknowledgments
This project was created as part of a statistical learning coursework by:
- Alvaro del Cañizo Angurel
- Javier Mascareña Gonzalez.
