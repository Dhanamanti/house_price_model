# house_price_model
House price prediction using Random Forest Regression, with data preprocessing, hyperparameter tuning, model evaluation, and price prediction.
# 🏠 Housing Price Prediction using Machine Learning

## 📌 Project Overview

This project predicts house prices using **Random Forest Regression**, a supervised Machine Learning algorithm. It uses housing features such as area, bedrooms, bathrooms, stories, parking spaces, and furnishing status to estimate house prices.

The project includes data preprocessing, categorical encoding, model training, performance evaluation, hyperparameter tuning, and model saving.

## 🎯 Objectives

- Preprocess and analyze housing data.
- Encode categorical features into numerical values.
- Train a Random Forest Regression model.
- Predict house prices on unseen test data.
- Evaluate the model using MAE, RMSE, and R² score.
- Tune hyperparameters using RandomizedSearchCV.
- Compare baseline and tuned model performance.
- Save and reload the trained model using Joblib.

## 📂 Dataset Information

- **Dataset:** Housing.csv
- **Total records:** 545
- **Original columns:** 13
- **Encoded input features:** 14
- **Target variable:** `price`

### Features Used

The dataset contains information about:

- Area
- Bedrooms
- Bathrooms
- Stories
- Main road access
- Guest room availability
- Basement availability
- Hot water heating
- Air conditioning
- Parking spaces
- Preferred area
- Furnishing status

The furnishing status column was converted into numerical features using one-hot encoding.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Joblib
- Google Colab
- GitHub

## ⚙️ Project Workflow

1. Load the housing dataset.
2. Separate input features (`X`) and target variable (`y`).
3. Encode categorical variables.
4. Split the dataset into training and testing sets (80:20).
5. Train a baseline Random Forest Regression model.
6. Generate house price predictions.
7. Evaluate model performance using regression metrics.
8. Perform hyperparameter tuning using RandomizedSearchCV.
9. Compare baseline and tuned models.
10. Save and reload the selected model.

## 🤖 Model Details

### Baseline Model

- Algorithm: Random Forest Regressor
- Number of trees: 100
- Random state: 42

### Hyperparameter Tuning

RandomizedSearchCV was used with 5-fold cross-validation to explore different parameter combinations.

Parameters explored:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `min_samples_leaf`
- `max_features`

**Best cross-validation R² score:** 0.6349

## 📊 Model Evaluation Results

Both models were evaluated on the same test dataset containing 109 houses.

| Evaluation Metric | Baseline Model | Tuned Model |
|---|---:|---:|
| MAE | ₹10,19,527.55 | ₹10,38,965.00 |
| RMSE | ₹14,00,219.42 | ₹14,22,354.00 |
| R² Score | 0.6121 | 0.5998 |

### Results and Observations

- The baseline model achieved an R² score of 0.6121.
- The tuned model achieved an R² score of 0.5998.
- The baseline model performed slightly better on this test split.
- Hyperparameter tuning did not improve test performance in this experiment.
- The results demonstrate the importance of evaluating tuned models on unseen data.

**Note:** R² is not the same as prediction accuracy. It measures how well the model explains variation in house prices relative to a mean-prediction baseline.

## 💾 Saving the Model

The baseline model was saved using Joblib.

```python
import joblib

joblib.dump(model, "housing_price_model.pkl")
```

To load the saved model:

```python
loaded_model = joblib.load("housing_price_model.pkl")

predictions = loaded_model.predict(X_test)
```

The input data must use the same feature names, column order, and encoding as the training data.

## 🚀 How to Run the Project

1. Clone or download this repository.
2. Open `Housing_Price_Prediction.ipynb` in Google Colab or Jupyter Notebook.
3. Upload `Housing.csv` or update the dataset path in the notebook.
4. Install the required dependencies.
5. Run the notebook cells in order.
6. Review the predictions, evaluation metrics, and model comparison.

Install dependencies using:

```bash
pip install -r requirements.txt
```

## 📁 Project Structure

```text
Housing-Price-Prediction-ML/
│
├── Housing_Price_Prediction.ipynb
├── Housing.csv
├── housing_price_model.pkl
├── requirements.txt
└── README.md
```

The saved model file is optional if you want users to train the model themselves. Include the dataset only if its license permits redistribution.

## 🔮 Future Improvements

- Experiment with Decision Tree, Gradient Boosting, and Extra Trees regressors.
- Perform feature engineering and outlier analysis.
- Evaluate model stability across different data splits.
- Improve hyperparameter search strategies.
- Develop a simple web application for interactive price predictions.

## 📚 Learning Outcomes

This project provided practical experience in:

- Data preprocessing and categorical encoding
- Supervised Machine Learning
- Regression model training and evaluation
- Hyperparameter tuning with cross-validation
- Model comparison and performance interpretation
- Saving and loading trained models

## 👩‍💻 Author

**Dhana Manti**

B.Tech – Electronics and Communication Engineering

Machine Learning Project
