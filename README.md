README: Lung Cancer Detection Model
This project documents the exploratory data analysis (EDA) and implementation of a Support Vector Classification (SVC) model for lung cancer detection based on a survey dataset.

💻 Project Overview
The goal of this project is to build and evaluate a machine learning model that predicts the likelihood of a person having lung cancer based on various health and lifestyle factors. The process involves data inspection, preprocessing (encoding and scaling), model training, and performance evaluation.

📊 Dataset Summary
The dataset, read from a CSV file named survey lung cancer.csv, contains 309 rows and 16 columns.




Columns & Data Types
The dataset features a mix of categorical (object) and numerical (int64) data types. All 309 entries for all columns are non-null.





Feature	Data Type	Description
GENDER	object	The only non-numerical input feature.
AGE	int64	Patient's age.
LUNG_CANCER	object	The target variable (Yes/No).
Other Features	int64		
13 other features like SMOKING, YELLOW FINGERS, ANXIETY, PEER PRESSURE, CHRONIC DISEASE, FATIGUE, ALLERGY, WHEEZING, ALCOHOL CONSUMING, COUGHING, SHORTNESS OF BREATH, SWALLOWING DIFFICULTY, and CHEST PAIN, likely encoded with numerical values (e.g., 1 and 2).






Export to Sheets
Target Variable Distribution
The LUNG_CANCER target variable is highly imbalanced.


YES (Cancer): 270 instances.




NO (No Cancer): 39 instances.



🛠️ Preprocessing and Model Training
1. Label Encoding
The categorical columns, 'LUNG_CANCER' and 'GENDER', were converted into numerical format using LabelEncoder.

2. Data Splitting
The data was split into feature set (x) and target variable (y), where the target is the LUNG_CANCER column.

A train-test split was performed, allocating 80% of the data for training and 20% for testing, with a random_state=42.


Test Size=0.2⟹62 samples (Total: 309 samples)




3. Feature Scaling
The features in the training and testing sets were scaled using StandardScaler to normalize the data.


4. Model Training
A Support Vector Classification (SVC) model was chosen and trained on the scaled training data (x_train,y_train).


📈 Model Performance
The SVC model achieved a high level of accuracy on both the training and testing sets:

Training Accuracy: 94.74%


Testing Accuracy: 96.77% 


Confusion Matrix
The confusion matrix for the test set (y_test) is:

( 
1
1
​
  
1
59
​
 )
Predicted NO (0)	Predicted YES (1)
Actual NO (0)	1 (True Negative)	1 (False Positive)
Actual YES (1)	1 (False Negative)	59 (True Positive)

Export to Sheets
The test set had 2 instances of 'NO' (0) and 60 instances of 'YES' (1).

Classification Report
Class	Precision	Recall	F1-Score	Support
0 (NO)	0.50	0.50	0.50	2
1 (YES)	0.98	0.98	0.98	60
Accuracy			0.97	62
Macro Avg	0.74	0.74	0.74	62
Weighted Avg	0.97	0.97	0.97	62

Export to Sheets
🔑 Key Observations

High Accuracy with Imbalance: The overall accuracy is high (0.97), but this is strongly influenced by the dominant 'YES' (Class 1) group, which has excellent precision and recall (0.98).


Poor Performance on Minority Class: The performance on the minority class 'NO' (Class 0) is significantly weaker, with a precision, recall, and F1-score of 0.50. This suggests the model has difficulty correctly identifying the 'NO' cases, which is a common issue with imbalanced datasets.

Correlation: The heatmap and correlation table show the linear correlation between features. Notably, the LUNG_CANCER target has the highest correlation with ALLERGY (0.327).
