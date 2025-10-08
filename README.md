# lung-cancer-detections
README: Lung Cancer Detection Model
This project outlines the steps taken to develop a machine learning model for Lung Cancer Detection using a survey dataset. The core of the analysis involves data preprocessing, exploratory data analysis, and training a Support Vector Classifier (SVC) model.

Dataset Overview
The dataset, read from the file survey lung cancer.csv, has the following characteristics:


Shape: 309 rows and 16 columns.


Data Types: 14 columns are int64 and 2 columns (GENDER and LUNG_CANCER) are object type.





Non-Null Count: All 16 columns have 309 non-null entries, indicating no missing values in the dataset.




Target Variable: The target variable is LUNG_CANCER.

Value Counts:


YES: 270 instances.


NO: 39 instances.

This distribution shows a high class imbalance, with a significantly greater number of 'YES' cases.



Data Preprocessing and Preparation

Label Encoding: The GENDER and LUNG_CANCER object columns were converted to numerical representations using LabelEncoder from sklearn.preprocessing.

Feature and Target Split:


Features (x): All columns except LUNG_CANCER.


Target (y): The LUNG_CANCER column.


Train-Test Split: The data was split into training and testing sets with a test size of 0.2 (20%) and a random_state of 42.


x_train, x_test, y_train, y_test = train_test_split(x,y,test_size=0.2,random_state=42).


Feature Scaling: The features were standardized using StandardScaler from sklearn.preprocessing.


Model Training and Evaluation
A Support Vector Classifier (SVC) model was chosen for the classification task.

Model Performance
Metric	Training Score	Testing Score
Accuracy	94.74%	96.77%
Confusion Matrix			
( 
1
1
​
  
1
59
​
 )



Export to Sheets

The model was trained on x_train and y_train, and then evaluated on both training and testing sets.


Classification Report (Test Set)
Class	Precision	Recall	F1-Score	Support
0	0.50	0.50	0.50	2
1	0.98	0.98	0.98	60
Accuracy			0.97	62
Macro Avg	0.74	0.74	0.74	62
Weighted Avg	0.97	0.97	0.97	62
