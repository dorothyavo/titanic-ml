# 🛳️ Titanic Survival Prediction – CSCI E-106 Group Project

**Harvard Extension School | CSCI E-106: Data Modeling**

This project explores survival prediction for Titanic passengers using statistical and machine learning models. Our goal was to analyze which features (such as class, age, fare, and gender) best predicted survival, and compare model performance across different algorithms.

---

## 📌 Project Summary

Using a cleaned dataset of 1,309 Titanic passengers, we:
- Engineered features from raw data (dummy variables, imputation, scaling)
- Trained classification models including:
  - Logistic Regression
  - Lasso Regression
  - Decision Trees
  - Random Forests
  - SVM
  - Neural Networks
- Evaluated models using confusion matrices, precision, recall, and F1 scores
- Selected the most effective model based on out-of-sample accuracy

🏆 **Champion model:** Decision Tree  
🎯 **Best F1 score:** Lasso Regression on test data (F1 = 0.7519)

---

## 📊 Key Features Used
- `pclass` (Passenger class)
- `sex` (Gender)
- `age` (Imputed using MICE)
- `fare` (Log-transformed, scaled)
- `embarked` (Port of embarkation)
- `sibsp` and `parch` (Family aboard, encoded as factors)
- `deck` (Extracted from `cabin`, then imputed)

---


---

## 🧠 Models & Results

| Model                 | Precision | Recall | F1 Score | Notes                             |
|----------------------|-----------|--------|----------|------------------------------------|
| Logistic Regression   | 0.7328    | 0.7111 | 0.7218   | Strong interpretability            |
| Lasso Regression      | 0.7634    | 0.7407 | 0.7519   | Best F1 score, good generalization |
| Decision Tree         | 0.752     | 0.674  | 0.712    | Best balance and visual clarity    |
| Random Forest         | –         | –      | –        | Tested, but not primary model      |

---

## 🧹 Data Cleaning Steps

- Dropped high-missing or non-predictive variables: `ticket`, `name`, `body`, `boat`, `home.dest`
- Imputed missing `age` with predictive mean matching (`mice`)
- Extracted deck from cabin and imputed
- Scaled continuous variables and created dummies for categorical ones
- Checked multicollinearity (VIF < 2)
- Used Hosmer-Lemeshow test for model fit

---

## 🛠 Tools & Libraries

- **Language:** R
- **Packages:** `ggplot2`, `mice`, `caret`, `rpart`, `randomForest`, `e1071`, `glmnet`, `nnet`
- **EDA:** Correlation plots, boxplots, decision tree diagrams

---

## 📌 Team Members
- Ana Duchini
- Douglas Malfacini
- Daniella Olivas
- John Pai
- Joseph Ross
- Kannan Sowminarayanan
- **Dorothy Vo**
- Thomas Yang
- Caroline Zhuo

---

## 📈 Key Takeaways

- Gender, class, and age were the strongest survival predictors.
- Lasso and Decision Trees outperformed basic logistic regression in generalizability.
- Ensemble methods like Random Forests show promise for future optimization.

---

## 📎 References

- [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)
- Faraway Package for Logistic Modeling
- MICE for Multiple Imputation in R

---

## 🧪 Run It Yourself

```r
# Clone the repo
git clone https://github.com/dorothyavo/titanic-ml.git
cd titanic-ml/scripts

# Run analysis
source("titanic_analysis.R")


