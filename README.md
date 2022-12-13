# BH-MLAI-Capstone-Project

Modeling And Data Analytics for the Prediction of Heart Disease Incidence using the Framingham Study Dataset.
By: Liat Genosar Roth, liat.gr@gmail.com

Jupiter Notebook: Capstone_project_liat.ipynb

Data Source:
https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression

DATA INSPECTION
1. This dataset contains 15 features columns, one target columns and 4238 entries. The target is TenYearCHD - the chance to get a Cardio-Vascular Disease (CVD) within 10 years.
2. All numeric dataset. 8 are real numbers, 7 categorical.
3. Few columns have missing values.

EDA
1. Ratio of target values in the dataset, and Amon men/women. Target: TenYearCHD.
2. Looking for correlations with the target column
3. Cross-tab gender and TenYearCHD: The chances of men to have heart disease within 10 years are 7% more than the women’s.
4. TenYearCHD by education level.
5. Glucose (level) by education level.
6. Total cholesterol, Sys. Blood Pressure analysis.
7. Heart Rate by TenYearCHD.
8. Bivariate analysis: current smoker by gender.

DATA PREP FOR MODELING
1. KNNImputer for filling missing values
2. Scaling the data using StandardScalert()

MODEL BUILDING
1. Dummy Classifier
2. Logistic Regression Model, GridSearchCV
    2.1 Accuracy, recall scores, Classification Report, Confusion Matrix.
    2.2 Coefs Importance
3. Random Forest Classifier
    3.1 Accuracy, recall scores, Classification Report, Confusion Matrix.
    3.2 Coefs Importance
    3.3 Running the model again with params change
4. Decision Tree, GridSearchCV
    4.1 Accuracy, recall scores, Classification Report, Confusion Matrix.
    4.2 Coefs Importance.
5. SVM GridSearchCV
    5.1 Accuracy, recall scores, Classification Report, Confusion Matrix.
6. KNN Classifier, GridSearchCV
    6.1 Accuracy, recall scores, Classification Report, Confusion Matrix.
    6.2 Coefs Partial Dependence.

Modeling with male and female datasets
1. Data preparation: KNNImputer, Scaling.
2. Logistic Regression grid search
3. SVM grid search

Summary of Results
1. All models comparison
2. Comparison for modeling men and women data
3. Comparing Coefs importance between models, and on the men-women modeling results.

Results: Table summarizing all models result.

                                                Train       Test
                                    mse	        Accuracy	Accuracy	Recall Score	TN,  FP,  FN, TP
Model					
Logistic Regression GridSearchCV	0.148113	0.857143	0.851887	0.080745	    [890,  9, 148, 13]
SVM GridSearchCV	                0.838679	0.158905	0.161321	0.900621	    [26,  873, 16, 145]
KNN GridSearchCV	                0.223585	1.000000	0.776415	0.198758	    [791, 108, 129, 32]
Decision Tree GridSearchCV	        0.157547	0.856514	0.842453	0.055901	    [884, 15,  152, 9]
Random Forest	                    0.151887	1.000000	0.848113	0.062112	    [889, 10,  151, 10]


Summary and Findings
1.SVM model did the best in predicting maximum true positive patients with the minimum false negatives, thus having the best recall score of 90.06%. This came with a low test accuracy of 16.13%. KNN model came second with a recall score of 19.88.
2. Best test accuracy score was achieved by the Logistic Regression model, 85.19%, which is only by little better than the dummy classifier. This can be explained by a relatively weak correlation between each of the dataset's 15 features and the target.
3. From separately analyzing and modeling the women and men data, and from comparing results with the general population dataset, I saw that better recall scores can be achieved by analyzing women and men data separately. The numbers for true positives and false negative were better.

Conclusions and Suggestions for Next Steps:

* My conclusion from the the modeling results is to give care providers a recommendation to treat much broader base of patients. When a model got it right predicting future CVD patients, it predicted a lot of false positives. When the accuracy was better with Logistic Regression model, it missed a lot of patients prone to have CVD. Risk for CVD is quite high as it is - 15%, and this is a condition that can be deadly when first appears, so any patient predicted to be at risk should be treated.

* Leading factors for predicting heart disease within 10 years are: age, cigarettes per day, systolic blood pressure, being male, prevalent stroke, and blood glucose levels.

* Modeling separately by gender gave better results and better predictive power. Thus my recommendation for care providers is treat men and women differently. Future research for the development of medications and diagnosis tools should be conducted in that view, so it is better targeted and accurate.

