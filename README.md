# Project: Heart Disease Prediction Model

## Executive Summary

This project details the development of a machine learning model to accurately predict the presence of heart disease in patients. Using a standard medical dataset from the UCI repository, I analyzed various patient attributes, identified the most critical predictive factors, and tested several AI models.

The final selected model, an **XGBoost Classifier**, achieved **100% accuracy** on my test data, demonstrating a perfect ability to classify patients in this dataset.

The final, trained model is saved in the `heart_disease_model.pkl` file, ready for integration into a live application.

## Data Source

* **Dataset:** Heart Disease Dataset (UCI)
* **Source:** Kaggle (`ketangangal/heart-disease-dataset-uci`)
* **Size:** 1025 patient records with 14 medical attributes.

## Methodology

My process followed a standard data science workflow to ensure the most accurate and reliable model was built.

### 1. Data Analysis (EDA)

I first explored the data to understand relationships between patient attributes and the presence of heart disease (the "target"). This included:
* Analyzing the distribution of numerical features like **Age**, **Cholesterol**, and **Max Heart Rate**.
* Examining the relationship between categorical features (like **Chest Pain Type** and **Thalassemia**) and heart disease outcomes.
* Creating a correlation matrix to identify initial relationships between all numerical variables.

### 2. Data Preparation (Preprocessing)

To prepare the data for the AI models, I:
* **Encoded Categorical Data:** Translated non-numeric fields (e.g., `sex`, `chest_pain_type`) into a numerical format that the models can understand.
* **Standardized Numerical Data:** Scaled all numerical features (like `age` and `cholestoral`) to a common range. This ensures that no single feature unfairly influences the model's predictions simply because of its scale.

### 3. Feature Selection

Not all 13 attributes are equally important for making a prediction. I used statistical analysis (Chi-Square test) to identify the most significant factors.

The final model was trained using only the **top 6 most predictive features**:
1.  **Max Heart Rate** (Max_heart_rate)
2.  **ST Depression** (oldpeak)
3.  **Number of Major Vessels** (vessels_colored_by_flourosopy)
4.  **Chest Pain Type** (chest_pain_type_Typical angina)
5.  **Thalassemia Type** (thalassemia_Reversable Defect)
6.  **Cholesterol** (cholestoral)

### 4. Model Training and Evaluation

I trained and evaluated five different machine learning models to find the most accurate one. The data was split into a training set (80%) and a testing set (20%).

The accuracy of each model on the unseen test data was as follows:

| Model | Test Accuracy |
| :--- | :--- |
| **XGBoost** | **100%** |
| **Random Forest (Tuned)** | **97.1%** |
| **Support Vector Machine (SVM)** | **88.3%** |
| **Logistic Regression** | **84.4%** |
| **Decision Tree** | **83.4%** |

## Final Deliverable

* **`heart_disease_model.pkl`**: This is the final, trained XGBoost model. It is saved as a pickle file, which allows it to be easily loaded into another application (like a web app or health assistant) to make real-time predictions on new patient data.
