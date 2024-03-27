# Diabetic Risk Assessment: Predictive Modeling for Early Detection of Diabetes

<p align="middle">
<img src="https://github.com/dimashidayat99/Diabetes_Prediction/assets/69446089/6166c210-c4f1-44a8-a16e-bde838481177"  width="800" />
</p>

# Project Background
The project focuses on predicting diabetes disease using the data provided by the user. 
This project will help benefit health organizations in reviewing the potential development of the disease among their clients. By detection, preventive measures can be taken to decrease the 
risk exhibited by the disease.

# Problem Statement
Diabetes is the most common disease caused by a group of metabolic disorders. These noncommutable diseases are also known as Diabetic mellitus. It affects the organs of the human 
body and disturbs their functionality. It can be controlled by predicting this disease earlier. If a diabetic patient is untreated for a long time, it may lead to increased blood sugar, which causes blindness, kidney failure, heart attacks, stroke, and lower limb amputation. In 2019, 9.3% of the world's population had diabetes, according to the International Diabetes Federation (IDF). If effective preventative strategies are not adopted, the figure is anticipated to climb to 10.2% by 2030 and 10.9% by 2045. Nowadays, Healthcare industries generate large volumes of data. Machine Learning algorithms and statistics are used to predict the disease with the help of current and past data. Machine learning techniques help doctors to predict the early stages of diabetics. Diabetic patient medical records and different types of algorithms are added to the dataset for experimental analysis. It is crucially important to design a machine learning algorithm that can predict diabetes through human lifestyle such as smoking and eating habits.

# Project Objective
1. To obtain the main factors of diabetes from the selected dataset using correlation 
analysis and exploratory data analysis.
2. To model the correlation between diabetes with demographic, lifestyle, physical, and 
mental health.
3. To build a data-driven medical diagnostic system to predict and early detect diabetes using 
machine learning.

# Dataset
The Behavioral Risk Factor Surveillance System (BRFSS) is a health-related telephone survey that is collected annually by the CDC. Each year, the survey collects responses from over 400,000 Americans on health-related risk behaviors, chronic health conditions, and the use of preventative services. It has been conducted every year since 1984. For this project, a CSV of the dataset available on Kaggle for the year 2015 was used. [dataset link](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset)

# EDA
## Descriptive Analysis

### Relation Between Binary Variables with the Target Variable (Diabetes Binary)

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Independent%20Variables%20vs%20Dependent%20Variable.png)

Based on the analysis of binary variables and target variables, some information is obtained:
1. Most diabetics tend to have high blood pressure.
2. Most diabetics tend to have high cholesterol.
3. Most diabetics have a cholesterol check in 5 years.
4. Smokers have minor to almost negligible effects on diabetes.
5. Most diabetics have no stroke. However, in fact, diabetes increases the risk 2 times to 
develop stroke.
6. Most diabetics have no heart disease or heart attack. However, in fact, diabetes 
increases the risk of developing heart disease and heart attack. Also, heart disease and 
heart attack increase the risk of developing diabetes.
7. Most diabetics have physical activity in the past 30 days.
8. Most diabetics consume veggies 1 or more per day.
9. Consuming fruit has a minor to almost negligible effect on diabetes.
10. Genders have negligible effect on diabetes.
11. Most diabetics do not a heavy alcohol consumption. However, due to the heavy alcohol 
consumption sample is limited. There is not enough information to support the conclusion.
12. Most diabetics have any kind of health care coverage.
13. Most diabetics have not seen a doctor because of no cost even needed in the past 
12 months.
14. Most diabetics have serious difficulty walking or climbing stairs.

### Combined Effects
#### Smoking, Alcohol Consumption, and Diabetes

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Smoker%2C%20Alcohol%2C%20Diabetes.png)

Based on the data, smoking together with heavy alcohol consumption increases the risk of 
developing diabetes.

#### High Blood Pressure, High Cholesterol and Diabetes

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Bp%2C%20Chol%2C%20Diabetes.png)

Based on the data, the combined effect of high blood pressure and high cholesterol increases risk 
of developing diabetes.

### Correlation Analysis

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Correlation%20Analysis%20on%20Diabetes.png)

Based on the correlation analysis, AnyHealthCare, NoDocbcCost, Fruits, and Sex are the least correlated with the target variable (Diabetes binary). All other variables have a significant correlation with the target variable (Diabetes binary).

# Modelling

For the modeling section, we have evaluated 7 established models such as Logistic 
Regression, Gaussian, K-NN, ExtraTree, RandomForest, Decision Tree, Lightgbm, and 
Xgboost; 2 balancing methods were used such as Near Miss downsampling and SMOTE 
upsampling; 3 feature scaling methods were used such as a standard scaler, min max scaler
and robust scaler; 3 feature selection methods were Pearson feature selection, 
chi-squared feature selection and random forest feature selection. The modeling phase was 
used all possible combinations of balancing method, feature scaling method, feature selection 
method and different algorithms to find the best models with the best method to get the maximum 
performance metrics. All the models were evaluated by using several metrics to measure the performance including accuracy, precision positive, precision negative, recall sensitivity, recall specificity, f1 positive, and f1 negative. All the models and methodologies were compared based on the evaluation metrics to find the best models and methods to analyze the data.

The best methodology and model will be used to undergo the optimization process known as hyperparameter tuning to find the best parameter of the models. The best methodology and the model were used to develop the data-driven diabetes prediction system. 

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Top%203%20Best%20Models%20%26%20Methods.png)

The evaluation results were filtered to finalize the best prediction model by increasing the benchmark of F1 Positive>0.9 and F1 Negative>0.91 as shown in the top 3 models figure. The best feature scaling method is not doing feature scaling, while the best data balancing technique is SMOTE upsampling. Both Random Forest and Lightgbm models can be used in this project since the difference between the evaluation metrics is not significant. However, it is found that the Lightgbm model with Random Forest features selection exhibits the fastest execution time, which is only about 7 seconds, as compared to others (Random Forest model with no features selection (~9 seconds) and Lightgbm with no features selection (~53 seconds)). Thus, Lightgbm with a random forest feature selection model (with no feature scaling and SMOTE upsampling) was selected as the best prediction model in this project.

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Performance%20Metrics%20Best%20Model.png)

The best model will be optimized to give the maximum potential of the model by finding the best parameter to used in the model. After Hyperparameter tuning of the model, a model able to achieve accuracy of 0.9098, precision positive of 0.9687, precision negative of 0.8641, recall sensitivity of 0.8466, recall specificity of 0.9727, F1 positive of	0.9035 and F1 negative of 0.9152. 

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Feature%20Importances.png)

Based on the features importance of the best model, the most important feature is BMI, followed by Age and General Health.


# Deployment
Anvil web application platform has been used to deploy the prediction model as a healthcare 
application to evaluate the tendency of the user to get diabetes or not. Anvil is a free Python-based drag-and-drop web app builder. Users can navigate the apps using either a desktop, laptop, tablet, or smartphone, which is very convenient to access. The Diabetes Prediction 
The app can be accessed through the [webpage link.](https://yiib2fcsyexhjsql.anvil.app/RJP4XN4VUDDQFDCAEM4WLZ7G)

# Further Reading
For further reading and understanding of this project, please move to the [code folder](https://github.com/dimashidayat99/Diabetes_Prediction/tree/main/code) where the source code can be found. There are more explanations, results, and findings in the source code.


