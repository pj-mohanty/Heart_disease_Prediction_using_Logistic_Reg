##Heart Disease Prediction: Data Preprocessing and Feature Engineering
###Introduction
This project focuses on analyzing heart disease data using machine learning techniques. The dataset contains various health metrics, such as age, gender, chest pain type, and cholesterol levels, along with a target variable indicating the presence of heart disease. The goal is to preprocess the data, perform feature engineering, and prepare it for model training.

### Inferences:
- **Major Vessels (ca)**: Higher numbers of major vessels colored by fluoroscopy correlate with heart disease.
- **Chest Pain Type (cp)**: Type 4 chest pain shows a higher presence of heart disease, suggesting it could be a significant predictor.
- **Exercise Induced Angina (exang)**: Those experiencing exercise-induced angina show higher proportions of heart disease.
- **Fasting Blood Sugar (fbs)**: There is a relatively equal distribution between those with and without high fasting blood sugar, indicating its limited effect on the target.
- **Gender**: Males exhibit a higher proportion of heart disease compared to females.
- **Resting Electrocardiographic Results (restecg)**: Type 2 results show a higher presence of heart disease.
- **Slope of the Peak Exercise ST Segment (slope)**: Type 2 slope suggests higher heart disease presence.
- **Thalium Stress Test Result (thal)**: A reversible defect in thal is associated with a higher heart disease presence.

### Summary:
- **Higher Impact on Target**: cp, exang, gender, slope, thal.
- **Moderate Impact on Target**: ca, restecg.
- **Lower Impact on Target**: fbs.

---

### Outlier Treatment

Outliers were identified in continuous features based on the Interquartile Range (IQR) method. The following outliers were found:

- **trestbps**: 9 outliers
- **chol**: 5 outliers
- **thalach**: 1 outlier
- **oldpeak**: 5 outliers
- **age**: No outliers

Due to the small size of the dataset, direct removal of outliers was avoided. Instead, transformations like Box-Cox were applied to reduce their impact.

---

### Data Preprocessing and Feature Engineering

1. **Stratified Train-Test Split**: The dataset was split into training and testing sets with a 20% test size, maintaining the proportion of heart disease cases in both sets.
2. **Numeric Feature Scaling**: Numeric features were transformed using Box-Cox to reduce skewness and improve the data's suitability for modeling. Some features like "oldpeak" showed improvement but could benefit from additional transformations.
3. **Categorical Feature Encoding**:
   - **Binary Features**: Features like "gender", "fbs", and "exang" were encoded using Label Encoding.
   - **Multiclass Features**: Features like "slope", "thal", "restecg", "cp", and "ca" were one-hot encoded to handle multiple categories.

After encoding and scaling, a combined feature matrix was created, ready for use in machine learning models.

---

This documentation provides a comprehensive overview of the data preprocessing and feature engineering steps applied to the heart disease prediction dataset.
