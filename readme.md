---

# Pima Indians Diabetes Prediction

## Overview
This project leverages the **Pima Indians Diabetes Dataset** to develop models for predicting diabetes diagnoses based on health and demographic factors. The dataset provides information on features like glucose level, blood pressure, BMI, and age, and the target variable represents diabetes diagnosis (1 = diabetic, 0 = non-diabetic).

## Project Structure
1. **Data Preprocessing**
2. **Model Selection**
3. **Evaluation Metrics**
4. **Results and Conclusion**

---

## 1. Dataset Overview and Preprocessing

The **Pima Indians Diabetes Dataset** includes data for female patients of Pima Indian heritage. Each record consists of:
- **Features**: Various health metrics (e.g., glucose, blood pressure, BMI).
- **Target**: Binary indicator for diabetes diagnosis (1 for diabetic, 0 for non-diabetic).

### Preprocessing Steps:
1. **Handling Missing Values**: Missing values were replaced with mean values to ensure data consistency.
2. **Feature Scaling**: Standardization was applied across all features to normalize the data, benefiting algorithms sensitive to feature scaling.

---

## 2. Model Selection

We explored five individual classifiers and an ensemble Voting Classifier:

1. **Logistic Regression**: Used as a baseline for binary classification tasks.
2. **Decision Tree**: Captures non-linear relationships, often effective with raw feature inputs.
3. **Random Forest**: An ensemble method that helps reduce overfitting seen in individual decision trees.
4. **Support Vector Machine (SVM)**: Effective in high-dimensional spaces with clear class separation.
5. **k-Nearest Neighbors (k-NN)**: Non-parametric, performs well with scaled features.
6. **Voting Classifier**: Combines the predictions of the individual models using soft voting to improve overall performance.

---

## 3. Model Evaluation Metrics

Each model was evaluated using these metrics:
- **Accuracy**: Measures overall correctness.
- **Precision**: Accuracy of positive (diabetes) predictions.
- **Recall**: Ability to identify actual positive cases.
- **F1 Score**: Harmonic mean of precision and recall.
- **ROC-AUC**: Area under the ROC curve, indicating the model’s discriminative ability.
- **Confusion Matrix**: A detailed count of true positives, false positives, true negatives, and false negatives.

### Model Performance Summary

| Model                | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|----------------------|----------|-----------|--------|----------|---------|
| Logistic Regression  | 0.7446   | 0.6774    | 0.5185 | 0.5874   | 0.8379  |
| Decision Tree        | 0.7619   | 0.7031    | 0.5556 | 0.6207   | 0.7144  |
| Random Forest        | 0.7532   | 0.6875    | 0.5432 | 0.6069   | 0.8184  |
| SVM                  | 0.7532   | 0.6875    | 0.5432 | 0.6069   | 0.8114  |
| k-NN                 | 0.7143   | 0.6154    | 0.4938 | 0.5479   | 0.7600  |
| Voting Classifier    | 0.7706   | 0.7258    | 0.5556 | 0.6294   | 0.8346  |

### Confusion Matrices and ROC Curves
The **Voting Classifier** and **Decision Tree** showed a good balance between true positives and low false negatives, essential for diabetes diagnosis. The **ROC-AUC** score for the Voting Classifier and Logistic Regression highlights their strength in distinguishing between diabetic and non-diabetic cases.

---

## 4. Results and Conclusion

### Best Performing Model
The **Voting Classifier** yielded the highest overall scores in key metrics, particularly:
- **Accuracy**: 0.7706
- **F1 Score**: 0.6294
- **ROC-AUC**: 0.8346

### Conclusion
The **Voting Classifier** combines strengths from various models, making it the preferred choice for diabetes prediction in this dataset. This ensemble approach strikes a balance between accuracy and sensitivity, which is crucial in healthcare applications.

### Recommendation
For production deployment, the Voting Classifier is recommended due to its consistent performance across multiple metrics. Ensemble models like this provide robust predictions in healthcare, where accuracy and sensitivity are paramount.

---