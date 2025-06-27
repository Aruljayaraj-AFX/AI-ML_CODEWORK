Australian Weather Prediction
Project Overview
This project aims to predict whether it will rain RainTomorrow in various locations across Australia based on daily weather observations. It leverages a dataset of meteorological records, applying various machine learning classification models to forecast future rainfall.

Dataset
The dataset used is weatherAUS.csv, which contains daily weather observations from different locations in Australia. The target variable for prediction is RainTomorrow, indicating whether it rained on the following day.

Key Features
The following features are utilized for prediction after preprocessing and feature selection:

MinTemp: Minimum temperature in degrees Celsius

MaxTemp: Maximum temperature in degrees Celsius

Rainfall: Amount of rainfall recorded in mm

Sunshine: Number of hours of bright sunshine in the day

WindGustSpeed: Speed of the strongest wind gust in km/h

WindSpeed9am: Wind speed at 9am in km/h

WindSpeed3pm: Wind speed at 3pm in km/h

Humidity9am: Humidity (percent) at 9am

Humidity3pm: Humidity (percent) at 3pm

Pressure9am: Atmospheric pressure (hpa) at 9am

Pressure3pm: Atmospheric pressure (hpa) at 3pm

Temp9am: Temperature (degrees Celsius) at 9am

Temp3pm: Temperature (degrees Celsius) at 3pm

Location: The location of the weather station

Preprocessing Steps
The raw dataset undergoes several preprocessing steps to prepare it for model training:

Column Dropping:

Irrelevant columns like Date, WindGustDir, WindDir9am, and WindDir3pm are removed.

Duplicate Handling:

Duplicate rows in the dataset are identified and removed to ensure data integrity and prevent bias.

Missing Value Imputation:

For numerical columns, missing values are filled with the mean of their respective columns.

For categorical columns (RainToday, RainTomorrow), missing values are imputed with the mode (most frequent value).

Categorical Feature Encoding:

Categorical features (Location, RainToday, RainTomorrow) are converted into numerical representations using LabelEncoder.

Data Type Conversion:

All relevant feature columns are converted to integer data types (int) for consistency and compatibility with models.

Outlier Removal:

Outliers in numerical columns are addressed using the Interquartile Range (IQR) method, though the current implementation only identifies the limits and doesn't explicitly filter them out in the provided snippet. For robust models, values outside these limits would typically be capped or removed.

Feature Selection
Feature selection is performed to identify the most impactful features for predicting RainTomorrow, reducing model complexity and improving performance.

Models Used for Importance: Both RandomForestClassifier and DecisionTreeClassifier are used to calculate feature importances.

Dropped Features: Based on the importance scores, the following features are dropped from the dataset as they showed lower predictive power: RainToday, Cloud9am, Evaporation, and Cloud3pm.

Machine Learning Models
The project evaluates the performance of several classification models:

Random Forest Classifier: An ensemble learning method that builds multiple decision trees and merges their predictions.

Decision Tree Classifier: A tree-structured classifier that makes decisions based on feature values.

Gradient Boosting Classifier: Another ensemble method that builds trees sequentially, with each tree correcting errors of the previous one.

Gaussian Naive Bayes: A probabilistic classifier based on Bayes' theorem, assuming independence between features.

K-Nearest Neighbors Classifier: A non-parametric method that classifies a data point based on the majority class of its 'k' nearest neighbors.

Logistic Regression: A linear model used for binary classification.

(Note: While the provided code snippet primarily details the Random Forest Classifier, the import statements suggest the intention to evaluate all listed models.)

Evaluation Metrics
The performance of each model is evaluated using the following metrics:

Recall Score: Measures the ability of the model to find all the positive samples.

Confusion Matrix: A table showing the performance of a classification model.

F1-Score: The harmonic mean of precision and recall.

Accuracy Score: The ratio of correctly predicted observations to the total observations.

ROC AUC Score: Measures the area under the Receiver Operating Characteristic curve, indicating the model's ability to distinguish between classes.

How to Run
To run this project, follow these steps:

Clone the Repository:

git clone <repository-url>
cd <repository-name>

Install Dependencies:
Make sure you have Python installed. Then, install the required libraries using pip:

pip install pandas seaborn matplotlib scikit-learn

Prepare the Dataset:
Place the weatherAUS.csv file in the same directory as the Python script.

Execute the Script:
Run the Python script:

python your_script_name.py

(Replace your_script_name.py with the actual name of your Python file.)

Results
The script will print out various details about the dataset, including information, descriptive statistics, head, tail, and null value counts. After preprocessing and model training, it will output the feature importances from Random Forest and Decision Tree models, followed by the evaluation metrics for the Random Forest Classifier (confusion matrix, recall, F1-score, accuracy, and AUC score). You can extend the script to print similar metrics for other models.
