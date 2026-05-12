# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
```
Step 1: Import Required Libraries

Import pandas, matplotlib, and sklearn modules for data handling, visualization, and ML.

Step 2: Load Dataset

Read Employee.csv using pandas.read_csv().

Step 3: Identify Target and Features

Target column → left (1 = employee left, 0 = stayed).

Features → satisfaction_level, last_evaluation, number_project, average_montly_hours, time_spend_company, Work_accident, promotion_last_5years, Departments, salary.

Step 4: Preprocess Data

Encode categorical variables (Departments, salary) into numeric values using Label Encoding.

Ensure no missing values exist.

Step 5: Split Dataset

Divide dataset into training set (70%) and testing set (30%) using train_test_split.

Step 6: Build Decision Tree Classifier

Initialize DecisionTreeClassifier with criterion = "entropy" (or "gini") and a maximum depth to prevent overfitting.

Train (fit) the model using training data.

Step 7: Make Predictions

Use the trained model to predict on the test data.

Step 8: Evaluate the Model

Measure performance using:

Accuracy Score

Confusion Matrix

Classification Report (Precision, Recall, F1-Score).

Step 9: Visualize the Decision Tree

Plot the decision tree using sklearn.tree.plot_tree to understand the decision rules.



```

## Program:
```python
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: sanjutha D
RegisterNumber:212225240136

# Decision Tree Classification Example

# Import libraries
import pandas as pd
import numpy as np

from sklearn.datasets import load_breast_cancer
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report
from sklearn import tree

import matplotlib.pyplot as plt

# Load dataset
data = load_breast_cancer()

# Input and Output
X = data.data
y = data.target

# Split dataset into training and testing
X_train, X_test, y_train, y_test = train_test_split(
    X, y,
    test_size=0.2,
    random_state=42
)

# Create Decision Tree model
model = DecisionTreeClassifier(
    criterion='entropy',
    max_depth=5,
    random_state=42
)

# Train model
model.fit(X_train, y_train)

# Predict output
y_pred = model.predict(X_test)

# Accuracy
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy)

# Confusion Matrix
cm = confusion_matrix(y_test, y_pred)
print("\nConfusion Matrix:")
print(cm)

# Classification Report
cr = classification_report(y_test, y_pred)
print("\nClassification Report:")
print(cr)

# Plot Decision Tree
plt.figure(figsize=(20,10))

tree.plot_tree(
    model,
    filled=True,
    feature_names=data.feature_names,
    class_names=data.target_names
)

plt.show()
  
*/
```

## Output:

<img width="567" height="311" alt="image" src="https://github.com/user-attachments/assets/94ed7302-11e3-4ce8-b5d4-5da8bfb99403" />


<img width="1130" height="558" alt="image" src="https://github.com/user-attachments/assets/4a669bb1-c0ea-46ae-b36e-f8befbd3d1d5" />


## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
