Titanic Survival Prediction using Scikit-learn Pipelines
🌟 Project Overview
This project implements an end-to-end Machine Learning workflow to predict survival on the Titanic, focusing on the rigorous application of Scikit-learn Pipelines and ColumnTransformer.

The primary goal is to demonstrate best practices for creating a robust and reusable ML pipeline that handles all data preprocessing, feature engineering, and modeling steps in a single, consistent unit, thereby preventing data leakage and streamlining deployment.

🛠️ Methodology: The ML Pipeline
The entire machine learning process is encapsulated in a single make_pipeline object, ensuring that all transformations are fitted only on the training data and then applied to both the training and test sets.

The pipeline consists of the following sequential steps:

trf1 (Imputation): Handles missing values.

Age: Uses SimpleImputer (default strategy: mean).

Embarked: Uses SimpleImputer with a most_frequent strategy.

trf2 (Encoding): Converts categorical features into a numerical format.

Sex & Embarked: Uses OneHotEncoder with handle_unknown='ignore' to manage potential new categories in the test set.

trf3 (Scaling): Scales all numerical features to a small, consistent range.

Uses MinMaxScaler to normalize features between 0 and 1.

trf4 (Feature Selection): Reduces dimensionality and improves model performance.

Uses SelectKBest with the χ 
2
  (chi-squared) test to select the top 8 features.

trf5 (Model Training): The final classification step.

Uses a Decision Tree Classifier.

💻 Repository Structure
File	Description
pipelines.py	The main script containing the full pipeline setup, training, prediction, and evaluation.
Titanic-Dataset.csv	The raw dataset used for training and testing.
README.md	This file, summarizing the project.

Export to Sheets
📈 Results and Evaluation
The model was trained and evaluated using 5-Fold Cross-Validation and further tuned using GridSearchCV to find the optimal hyperparameters.

Metric	Decision Tree Classifier Score
Best Accuracy Score	[INSERT FINAL ACCURACY HERE]
Best Cross-Validation Score (Mean)	[INSERT CROSS-VAL SCORE HERE]
Best Hyperparameters	[e.g., {'max_depth': 7, 'min_samples_leaf': 5}]

Export to Sheets
🚀 Setup and Installation
To run this project locally, you need Python and the following libraries:

Bash

pip install numpy pandas scikit-learn
Run the Script
Bash

python pipelines.py
💡 Future Enhancements
Compare the performance of the Decision Tree against a Random Forest and Support Vector Machine (SVM) classifier.

Perform more extensive Exploratory Data Analysis (EDA) and visualize feature importance.

Utilize Pipeline caching to speed up repeated tuning iterations.







