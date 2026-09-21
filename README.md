# Jamboree Education — Graduate Admission Analysis

## 📓 Run the Analysis in Google Colab

[![Open in Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1YWLy3G5pXCFjsY4uwMrHuS4QcyMZKfXG?usp=sharing)
## 📌 Project Overview

Jamboree Education has introduced a feature that allows students to estimate their probability of admission to Ivy League colleges from an Indian applicant's perspective.

The objective of this project is to analyze the factors associated with graduate admission chances and build a **Linear Regression model** to estimate an applicant's `Chance of Admit`.

The analysis covers data exploration, preprocessing, exploratory data analysis, correlation analysis, statistical modeling, linear regression assumptions, and model evaluation.

---

## 🎯 Business Problem

Jamboree wants to better understand the factors associated with graduate admission chances so that it can:

* Identify important variables associated with admission probability.
* Understand relationships between applicant characteristics and admission chances.
* Build a model that can provide an estimated admission probability.
* Use these insights to provide more personalized guidance to students.

---

## 📊 Dataset

The dataset contains **500 applicants and 9 columns**.

### Features

| Column              | Description                                                               |
| ------------------- | ------------------------------------------------------------------------- |
| `Serial No.`        | Unique identifier for each applicant                                      |
| `GRE Score`         | GRE score, measured on a scale of 0–340                                   |
| `TOEFL Score`       | TOEFL score, measured on a scale of 0–120                                 |
| `University Rating` | University rating on a scale of 0–5                                       |
| `SOP`               | Strength of Statement of Purpose, rated 0–5                               |
| `LOR`               | Strength of Letter of Recommendation, rated 0–5                           |
| `CGPA`              | Undergraduate CGPA, measured on a scale of 0–10                           |
| `Research`          | Indicates whether the applicant has research experience (1 = Yes, 0 = No) |
| `Chance of Admit`   | Estimated admission probability, ranging from 0–1                         |

---

## 🛠️ Tools & Technologies

* **Python**
* **Pandas** — Data manipulation and preprocessing
* **NumPy** — Numerical computations
* **Matplotlib** — Data visualization
* **Seaborn** — Statistical visualization
* **Statsmodels** — Statistical modeling and hypothesis testing
* **Scikit-learn** — Machine learning and model evaluation
* **Google Colab** — Development environment

---

## 🔎 Project Workflow

### 1. Data Understanding & Preprocessing

The dataset was examined for:

* Dataset dimensions
* Data types
* Missing values
* Duplicate records
* Descriptive statistics
* Outliers

### 2. Exploratory Data Analysis

The following analyses were performed:

* Distribution analysis using histograms
* Outlier detection using boxplots
* Categorical feature analysis using barplots
* Correlation analysis using a heatmap
* Relationship analysis between predictors and `Chance of Admit`

### 3. Statistical Analysis

Correlation analysis was used to understand the pairwise linear relationships between variables.

The analysis indicated that **CGPA had the highest correlation with `Chance of Admit`** among the variables examined.

> Correlation does not imply causation, and a high pairwise correlation does not automatically mean that a feature is the most important predictor in a multivariate model.

---

## 🤖 Linear Regression Model

A **Multiple Linear Regression** model was developed to estimate `Chance of Admit` using the applicant characteristics.

The dataset was divided into:

* **80% Training data**
* **20% Testing data**

The features were standardized before modeling.

### Feature Significance

The initial regression model contained two predictors with p-values greater than 0.05.

Those predictors were removed and the model was retrained.

In the second model, the remaining predictors had p-values below 0.05.

Among the remaining predictors, **CGPA showed the largest estimated positive association with `Chance of Admit`**, while holding the other predictors constant.

---

## 🧪 Linear Regression Assumptions

The regression model was evaluated against the following assumptions:

1. Multicollinearity
2. Mean of residuals approximately equal to zero
3. Linear relationship
4. Homoscedasticity
5. Normality of residuals

### Multicollinearity — VIF

Variance Inflation Factor (VIF) was used to assess multicollinearity between predictors.

The analysis used a VIF threshold of 5 for identifying potentially problematic multicollinearity.

### Mean of Residuals

The mean residual was found to be very close to zero, which is consistent with the expected behavior of the regression residuals.

### Linearity

Scatter plots were examined to assess whether the relationship between the predictors and `Chance of Admit` could reasonably be represented using a linear relationship.

The analysis showed upward trends for variables including:

* CGPA
* GRE Score
* TOEFL Score
* LOR

### Homoscedasticity

A residual analysis and the Goldfeld-Quandt test were used to assess whether the variance of the residuals was approximately constant.

The Goldfeld-Quandt test produced a p-value of approximately **0.61**, providing no strong statistical evidence of heteroscedasticity at the 5% significance level.

### Normality of Residuals

The normality assumption was **not satisfied**.

The residual histogram showed noticeable skewness, including a heavier negative tail, while the Q-Q plot showed substantial deviation from the reference line.

This limitation should be considered when interpreting the regression model and its statistical inference.

---

## 📈 Model Performance

The final model was evaluated on unseen test data.

| Metric      |     Result |
| ----------- | ---------: |
| **Test R²** | **0.8155** |
| **MAE**     | **0.0429** |
| **RMSE**    | **0.0614** |

### Interpretation

**R² = 0.8155**

The model explains approximately **81.55% of the variation** in `Chance of Admit` on the test dataset.

**MAE = 0.0429**

On average, the model's predicted admission probability differs from the actual value by approximately **0.043**.

**RMSE = 0.0614**

RMSE is slightly higher than MAE, indicating that some predictions have relatively larger errors.

The training R² was approximately **0.821**, compared with a test R² of **0.8155**. The relatively small difference suggests similar performance on the training and unseen test datasets.

---

## 💡 Key Insights

1. The dataset contains **500 observations and 9 columns**.

2. No missing values or duplicate records were found during the initial data quality checks.

3. The continuous variables showed relatively few extreme outliers.

4. The applicant pool generally had relatively high GRE, TOEFL and CGPA values.

5. **CGPA showed the strongest pairwise correlation with `Chance of Admit`** in the correlation analysis.

6. GRE and TOEFL scores also showed positive relationships with admission chances.

7. Research experience, SOP, LOR and university rating were examined as part of the applicant profile.

8. The regression model achieved a test **R² of 0.8155**, indicating that the selected predictors explain a substantial portion of the variation in the target variable.

9. The **normality assumption of the regression residuals was not satisfied**, which is an important limitation of the model.

---

## 💼 Business Recommendations

Based on the analysis:

### 1. Focus on Academic Performance

Jamboree can place greater emphasis on an applicant's academic performance, particularly CGPA, when providing personalized guidance.

### 2. Support GRE & TOEFL Preparation

Since stronger GRE and TOEFL scores are positively associated with admission chances, Jamboree can provide targeted preparation and retake guidance where appropriate.

### 3. Encourage Relevant Research Experience

Students can be encouraged to develop relevant research experience when it aligns with their intended field of study and application goals.

### 4. Improve Recommendation Letter Guidance

Jamboree can guide students in selecting suitable recommenders and developing strong, relevant Letters of Recommendation.

### 5. Evaluate the Complete Applicant Profile

Admission chances should not be evaluated using a single variable. Jamboree should consider the applicant's overall profile when providing admission guidance.

---

## ⚠️ Limitations

* The dataset contains **500 observations**, so the findings should not automatically be generalized to all graduate applicants.
* `Chance of Admit` represents an estimated probability in the dataset and should not be interpreted as a guaranteed admission probability.
* The regression residuals did **not satisfy the normality assumption**.
* Correlation analysis describes association and does not establish causation.
* The model is based on the variables available in the dataset and may not capture other factors involved in real-world admissions.

---


##  Project Structure

```text
Jamboree-Education-Case-Study/
│
├── Jamboree_Education_Case_Study(1).ipynb
├── Jamboree_Admission.csv
└── README.md
```

---

##  Project Focus

This project demonstrates an end-to-end **Data Analysis + Statistical Modeling** workflow, including:

**Data Cleaning → EDA → Correlation Analysis → Feature Analysis → Linear Regression → Assumption Testing → Model Evaluation → Business Recommendations**
