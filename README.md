# Project Background
The project focuses on predicting the diabetes disease using the data provided by the user. 
This project will help benefit health organizations in reviewing the potential development of the disease among their clients. By detection, preventive measures can be taken to decrease the 
risk exhibited by the disease.

# Problem Statement
Diabetes is a most common disease caused by a group of metabolic disorders. This non 
commutable diseases are also known as Diabetic mellitus. It affects the organs of the human 
body and disturbs their functionality. It can be controlled by predicting this disease earlier. If diabetics patient is untreated for a long time, it may lead to increase blood sugar, which cause of blindness, kidney failure, heart attacks, stroke and lower limb amputation. In 2019, 9.3% of world population have diabetes, according to the International Diabetes Federation (IDF). If effective preventative strategies are not adopted, the figure is anticipated to climb to 10.2% by 2030 and 10.9% by 2045. Now a days, Healthcare industries generating large volume of data. Machine Learning algorithms and statistics are used to predict the disease with the help of current and past data. Machine learning techniques helps the doctors to predict early stage for diabetics. Diabetics patient medical record and different types of algorithms are added in dataset for experimental analysis. It is crucially important to design a machine learning algorithm that can predict diabetes though human lifestyle such as smoking and eating habits.

# Project Objective
1. To obtain the main factors of diabetes from the selected dataset using correlation 
analysis and exploratory data analysis.
2. To model the correlation between diabetes with demographic, lifestyle, physical and 
mental health.
3. To build a data driven medical diagnostic system to predict and early detect diabetes using 
machine learning.

# Dataset
The Behavioral Risk Factor Surveillance System (BRFSS) is a health-related telephone survey that is collected annually by the CDC. Each year, the survey collects responses from over 400,000 Americans on health-related risk behaviors, chronic health conditions, and the use of preventative services. It has been conducted every year since 1984. For this project, a csv of the dataset available on Kaggle for the year 2015 was used. [dataset link](https://www.kaggle.com/datasets/alexteboul/diabetes-health-indicators-dataset)

# EDA
## Descriptive Analysis

### Relation Between Binary Variables with the Target Variable (Diabetes Binary)

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Independent%20Variables%20vs%20Dependent%20Variable.png)

Based on the analysis of binary variables and target variable, some information is obtained:
1. Most diabetic tend to have high blood pressure.
2. Most diabetic tend to have high cholesterol.
3. Most diabetic having cholesterol check in 5 years.
4. Smoker have minor to almost negligible effect on diabetes.
5. Most diabetic have no stroke. However, in fact, the diabetes increase risk 2 times to 
develop stroke.
6. Most diabetic have no heart disease or heart attack. However, in fact, diabetes 
increase risk to develop heart disease and heart attack. Also, heart disease and 
heart attack increase risk to develop diabetes.
7. Most diabetic having physical activity in the past 30 days.
8. Most diabetic consume veggies 1 or more per day.
9. Consuming fruit have minor to almost negligible effect on diabetes.
10. Genders have have negligible effect on diabetes.
11. Most diabetic not a heavy alcohol consumption. However, due to the heavy alcohol 
consumption sample is limited. It is not enough information to support the conclusion.
12. Most diabetic have any kind of health care coverage.
13. Most diabetic have not seeing doctor because of no cost even is needed in the past 
12 months.
14. Most diabetic having serious difficulty walking or climbing stairs.

### Combined Effects
#### Smoking, Alcohol Consumption and Diabetes

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Smoker%2C%20Alcohol%2C%20Diabetes.png)

Based on the data, smoking together with heavy alcohol consumption increase risk of 
developing diabetes.

#### High Blood Pressure, High Collesterol and Diabetes

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Bp%2C%20Chol%2C%20Diabetes.png)

Based on the data, combine effect of high blood pressure and high cholesterol increase risk 
of developing diabetes.

### Correlation Analysis

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Correlation%20Analysis%20on%20Diabetes.png)

Based on the correlation analysis, AnyHealthCare, NoDocbcCost, Fruits and Sex are the least correlated with the target variable (Diabetes binary). All other variables have a significant correlation with the target variable (Diabetes binary).

# Modelling

For the modelling section, we have evaluated 7 established models such as Logistic 
Regression, Gaussian, K-NN, ExtraTree, RandomForest, Decision Tree, Lightgbm, and 
Xgboost; 2 balancing method were used such as Near Miss downsampling and SMOTE 
upsampling; 3 feature scaling method were used such as standard scaler, min max scaler
and robust scaler; 3 feature selection method were such as pearson feature selection, 
chi squared feature selection and random forest feature selection. The modelling phase was 
used all possible combination of balancing method, feature scaling method, feature selection 
method and different algorithm to find the best models with the best method to get maximum 
performance metrics. All the models were evaluated by using several metrics to measure the performance including accuracy, precision positive, precision negative, recall sensitivity, recall specitivity, f1 positive and f1 negative. All the models and methodology was compared based on the evaluation metrics to find the best models and methods to analyzed the data.

The best methodology and model will be used to undergo the optimization process known as hyperparameter tuning to find the best parameter of the models. The best methodology and the model was used to develop the data driven diabetes prediction system. 

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Top%203%20Best%20Models%20%26%20Methods.png)

The evaluation results were filtered to finalized the best prediction model by increasing the benchmark of F1 Positive>0.9 and F1 Negative>0.91 as shown in the top 3 models figure. The best feature scaling method is to not doing feature scaling, while the best data balancing technique was SMOTE upsampling. Both Random Forest and Lightgbm model can be used in this project since the difference between the evaluation metrics is not significant. However,it is found that the Lightgbm model with Random Forest features selection exhibit the fastest execution time, which only about 7 seconds, as compared to others (Random Forest model with no features selection (~9 second) and Lightgbm with no features selection (~53 second)). Thus, Lightgbm with random forest feature selection model (with no feature scaling and SMOTE upsampling) was selected at the best prediction model in this project.

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Performance%20Metrics%20Best%20Model.png)

The best model will be optimized to give maximum potential of the model by finding the best parameter to used in the model. After Hyperparameter tuning of the model, model able to achieve accuracy of 0.9098, precision positive of 0.9687, precision negative of 0.8641, recal sensitivity of 0.8466, recall specitivity of 0.9727, F1 positive of	0.9035 and F1 negative of 0.9152. 

![](https://github.com/dimashidayat99/Diabetes_Prediction/blob/main/result/Feature%20Importances.png)

Based on the features importance of the best model, the most important features is BMI, followed by Age and General Health.


# Deployment
Anvil web application platform has been used to deploy the prediction model as a healthcare 
application to evaluate the tendency of the user to get diabetes or not. Anvil is a free Pythonbased drag-and-drop web app builder. User can navigate the apps using either desktop, laptop, tablet, or smartphone, which is very convenient to access. The Diabetes Prediction 
App can be access through the [webpage link.](https://yiib2fcsyexhjsql.anvil.app/RJP4XN4VUDDQFDCAEM4WLZ7G)

# Further Reading
For further reading and understanding this project, please move to the [code folder](https://github.com/dimashidayat99/Diabetes_Prediction/tree/main/code) where the source code can be found. There are more explanations, results and findings in the source code.


