
![Heart_Disease](https://github.com/user-attachments/assets/e1379534-80c8-4676-990c-7b58d2162055)


# Heart-Disease-Prediction

## Project Overview
This project builds and compares machine learning models to predict heart disease using patient data. It includes data preprocessing, feature engineering, and performance evaluation using Logistic Regression, Naive Bayes, Random Forest, and a Voting Classifier Ensemble.

## Heart Disease Dataset – Feature Dictionary

| Feature        | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `age`          | Age of the patient (in years)                                               |
| `sex`          | Sex (1 = male, 0 = female)                                                  |
| `cp`           | Chest pain type (0–3): <br> 0 = typical angina, 1 = atypical angina, <br> 2 = non-anginal pain, 3 = asymptomatic |
| `trestbps`     | Resting blood pressure (in mm Hg on admission to the hospital)              |
| `chol`         | Serum cholesterol in mg/dl                                                  |
| `fbs`          | Fasting blood sugar > 120 mg/dl (1 = true, 0 = false)                       |
| `restecg`      | Resting electrocardiographic results (0–2)                                  |
| `thalach`      | Maximum heart rate achieved                                                 |
| `exang`        | Exercise-induced angina (1 = yes, 0 = no)                                   |
| `oldpeak`      | ST depression induced by exercise relative to rest                          |
| `slope`        | Slope of the peak exercise ST segment (0 = upsloping, 1 = flat, 2 = downsloping) |
| `ca`           | Number of major vessels (0–3) colored by fluoroscopy                        |
| `thal`         | Thalassemia (1 = normal; 2 = fixed defect; 3 = reversible defect)            |
| `target`       | Heart disease presence (1 = has disease, 0 = no disease)                    |

## Dataset
- **Source**: UCI Heart Disease dataset
- **Target variable**: `target` (0 = No Disease, 1 = Disease)
- **Key features**: age, sex, cholesterol, max heart rate (thalach), resting blood pressure, chest pain type, etc.

## EDA & Feature Engineering
- Binned numerical features like `age`, `chol`, and `thalach` into quartiles for clearer visualization and analysis
- Visualized both **prevalence (rate of disease in groups)** and **incidence (count of disease cases)** by sex, age group, and cholesterol level
- Handled missing values and standardized numerical features
- Created confusion matrices to understand true vs. false positives and negatives across all models

## Models Compared
| Model               | Accuracy | F1 Score (Disease) | Recall (Disease) |
|--------------------|----------|--------------------|------------------|
| Logistic Regression| 80%      | 0.83               | 0.91             |
| Naive Bayes        | 82%      | 0.85               | 0.91             |
| Random Forest      | **84%**  | **0.86**           | **0.97**         |
| Ensemble (Voting)  | 82%      | 0.85               | 0.94             |

## Conclusion
Random Forest and the Ensemble model demonstrated the highest recall for disease detection, which is critical in healthcare scenarios where identifying patients at risk is a priority. All models showed strong generalization, confirming machine learning's effectiveness in clinical prediction tasks.

By analyzing **both prevalence and incidence** across demographic and physiological categories, we identified patterns such as:
- Higher disease rates in males compared to females
- Increased incidence with age and elevated cholesterol
- Key features like `thalach` (max heart rate) acting as indicators of heart condition

### Ensemble Model Detailed Report
```
              precision    recall  f1-score   support

  No Disease       0.90      0.68      0.78        28
     Disease       0.78      0.94      0.85        33

    accuracy                           0.82        61
   macro avg       0.84      0.81      0.81        61
weighted avg       0.83      0.82      0.82        61
```

This high recall ensures the model captures most disease cases, reducing false negatives, that is critical in medical diagnostics. Although it slightly overpredicts disease (with lower recall for “No Disease”), this is acceptable in contexts where missing an at-risk patient is costlier than a false alarm.

## Key Business & Clinical Queries This Project Addresses
- What age and sex groups show the highest **prevalence and incidence** of heart disease?
- Which health metrics are most predictive of heart disease?
- Can we accurately predict high-risk individuals using existing patient data?
- What is the impact of combining models via ensembling on diagnostic accuracy?
- How does model sensitivity affect the balance between false positives and false negatives?

## Future Work
- Incorporate hyperparameter tuning (GridSearchCV or Optuna)
- Build an interactive dashboard using Streamlit
- Validate models on external or real-time datasets
- Apply SHAP or LIME for feature importance interpretation in clinical context

## Contact
Created by Khevendra Singh — feel free to fork, clone, or connect for collaboration!
