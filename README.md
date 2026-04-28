# 🚗 Car Price Prediction Machine Learning Project

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-orange?logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-green.svg)

## 📖 Overview

This project aims to predict the selling price of used cars based on various features such as present price, kilometers driven, fuel type, seller type, and transmission. By leveraging Machine Learning regression algorithms, the model assists users and dealerships in estimating the market value of a vehicle accurately.

The solution involves a complete data science pipeline, from exploratory data analysis (EDA) and preprocessing to model training and evaluation.

## ✨ Features

- **Comprehensive EDA:** Visual analysis of relationships between car features and selling prices.
- **Data Preprocessing:** Handling categorical data, feature scaling, and outlier management.
- **Multiple Algorithms:** Comparison of Linear Regression, Random Forest, and other regressors.
- **High Accuracy:** Optimized model achieving a high R² score on test data.
- **Model Persistence:** Saved model files (`.pkl`) for easy deployment and inference.

## 🛠️ Tech Stack

| Category | Tools & Libraries |
| :--- | :--- |
| **Language** | Python 3.8+ |
| **Data Manipulation** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Machine Learning** | Scikit-Learn |
| **Environment** | Jupyter Notebook, Google Colab |

## 📊 Dataset

The dataset contains information about used cars listed for sale. Key features include:

- `Car_Name`: Name of the car.
- `Year`: Manufacturing year.
- `Selling_Price`: The price at which the car is sold (Target Variable).
- `Present_Price`: Current ex-showroom price of the car.
- `Kms_Driven`: Total kilometers driven by the car.
- `Fuel_Type`: Type of fuel (Petrol, Diesel, CNG).
- `Seller_Type`: Whether the seller is a dealer or individual.
- `Transmission`: Manual or Automatic.
- `Owner`: Number of previous owners.

## 🚀 Methodology

### 1. Data Cleaning
- Checked for null values and duplicates.
- Derived a new feature `Age` from the `Year` column to represent the car's age.

### 2. Exploratory Data Analysis (EDA)
- Analyzed the distribution of selling prices.
- Visualized correlations between numerical features using Heatmaps.
- Examined the impact of Fuel Type and Transmission on price.

### 3. Preprocessing
- **Encoding:** One-Hot Encoding applied to categorical columns (`Fuel_Type`, `Seller_Type`, `Transmission`).
- **Feature Selection:** Removed redundant columns to prevent multicollinearity.
- **Splitting:** Data split into Training (80%) and Testing (20%) sets.

### 4. Model Training
Several regression models were evaluated:
1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

**Selected Model:** Random Forest Regressor demonstrated the best performance in terms of generalization and error metrics.

### 5. Evaluation Metrics
- **R² Score:** Measures the proportion of variance in the dependent variable predictable from the independent variables.
- **MAE (Mean Absolute Error):** Average magnitude of errors in a set of predictions.


## 📋 Installation & Usage

Follow these steps to run the project locally:

### 1. Clone the Repository
```bash
git clone https://github.com/Vedhinee/Car-Price-Prediction.git
cd Car-Price-Prediction


### 2. Create Virtual Environment (Optional)
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate


### 3. Install Dependencies
```bash
pip install -r requirements.txt


### 4. Run the Notebook
Open the Jupyter Notebook file to explore the code and visualizations:
```bash
jupyter notebook car_price_prediction.ipynb


### 5. Load the Model for Prediction
To use the saved model for new predictions
import pickle
import numpy as np

# Load the model
with open('car_price_model.pkl', 'rb') as f:
    model = pickle.load(f)

# Example prediction input (ensure shape matches training data)
input_data = np.array([[2015, 10.50, 50000, 0, 1, 0, 1, 0, 0]]).reshape(1, -1)
prediction = model.predict(input_data)

print(f"Predicted Selling Price: {prediction[0]}")

Future Scope
- Web Application: Deploy the model using Streamlit or Flask for a user-friendly interface.
- Feature Engineering: Incorporate more features like car brand reputation, location, and insurance validity.
- Deep Learning: Experiment with Neural Networks for potentially higher accuracy on larger datasets.
