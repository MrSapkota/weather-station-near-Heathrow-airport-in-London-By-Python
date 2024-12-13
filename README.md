# weather-station-near-Heathrow-airport-in-London-By-Python
Its a Predictive Analytics Project using python 



DATA DESCRIPTION

For the purpose of regression analysis, we are using the "weather.csv" dataset. The measurement of this dataset were recorded by a weather station near Heathrow airport in London, UK. There are 10 attributes to the data set:

date - recorded date of measurement

cloud_cover - cloud cover measurement in oktas

sunshine - sunshine measurement in hours

global_radiation - irradiance measurement in Watt per square meter

max_temp - maximum temperature recorded in degrees Celsius

mean_temp - mean temperature in degrees Celsius

min_temp - minimum temperature recorded in degrees Celsius

precipitation - precipitation measurement in millimeters

pressure - pressure measurement in Pascals

snow_depth - snow depth measurement in centimeters

TARGET VARIABLE

A target variable selected is max_temp for which we are going to predict the maximum temperature for the day using three different analysis, names, linear regression, logistic regression and the rigid regression analysis.

QUESTION 1: LINEAR REGRESSION MODEL

A linear regression model is the method to discover the association between a target variable and one or more predictors by fitting a linear equation on observed data. It can either be,

i) A simple Linear Regression ii) Multiple Linear Regression
In a simple linear regression, there is one target and one predictor variable but in multiple regression tehre are more than one predictors. There are different methods to find the parameters of a linear models, they are, Ordinary Least Square(OLS) method, Gradient Descent method, and using a python libraries with built in functions.

Given below are the steps followed in order to find the parameter of the linear model.

Step1: Loading and Viewing the dataset

Step2: Data Cleaning and Pre-Processing

Step3: Selecting relevant features using feature selection technique, that is,

Step3: Spilitting the data into training and test dataset.

Step4: Building a linear regression model using OLS method and Gradient Descent methods on train data set.

Step5: Predicting the target data on train data and test data set.

Step6: Checking the accuracy of the models based on the following factors: R-Squared value and Mean Squared Error (MSE)

Step7: Visualizing the model

![image](https://github.com/user-attachments/assets/98bdeee2-45dd-4a85-b426-f4f900c1a8c5)

![image](https://github.com/user-attachments/assets/f6f06b52-2481-485c-af09-1478b89d93b3)

![image](https://github.com/user-attachments/assets/d78c991f-f817-4ecc-b31f-d31b897f1bca)

![image](https://github.com/user-attachments/assets/95c15b8e-be68-4190-863f-9b2c8209bd7a)

DATA CLEANING AND PRE-PROCESSING

In this step, we checked for missing values and dropped the rows with missing values.

![image](https://github.com/user-attachments/assets/fd5d006e-bb04-4943-9955-1a68d219f7f0)

![image](https://github.com/user-attachments/assets/f58d5184-8df5-467e-b9c3-3af770c63a97)

This heatmap reveals how strongly or weakly two attributes are related.

SETTING TARGET VARIABLE (y) and PREDICTORS (X)

In order to select the target variable we mention the name of the column from the weather dataset and store the values in y

![image](https://github.com/user-attachments/assets/5c00b996-cdc4-4920-b035-a23be1b57023)

SETTING LIST OF PREDICTORS IN X

In order to set list of predictor in X, we drop the column that we have set as our target variable from the weather dataset.

![image](https://github.com/user-attachments/assets/43169417-6541-4f9c-9605-66a35176cf79)

DATA SCALING

At this stage, we transform our data to have zero mean and variance of 1. This is done to normalize the data so that there wont be a vast difference between the range of values that the features holds.

![image](https://github.com/user-attachments/assets/6fb24a61-64db-4d23-8df4-194745d562d2)

FEATURE SELECTION

The best features to predict max_temp of the day is selected using the technique called SelectKBest and f_regression

![image](https://github.com/user-attachments/assets/d602503b-baff-480b-921b-350899341ed1)

DIVIDING THE DATASET

For the purpose of building the models, split the dataset into train and test dataset. Then the model is build on train dataset and prediction is done on both train and test set. Splitting is done using Scikit-learn package train_test_split function. 80 percentage of the data is used as train data while remaining 20 percentage as test data.


![image](https://github.com/user-attachments/assets/8de8ff4c-ab54-43a6-b093-6cea646d9727)


QUESTION 1 (METHOD1): LINEAR MODEL USING LINEAR REGRESSION FUNCTION (OLS) in SCIKIT-LEARN

![image](https://github.com/user-attachments/assets/c0f41881-6610-4f71-b812-d8c699efef06)

The above results shows that in both train and test dataset, the model is able to explain 87 percentage of the variance. In addition, the MSE for train data is 5.41 and for test data is 5.43 which are a small difference therefore, it can be said that model performs well and model predictors aligns well with the true values.


LINEAR MODEL PLOT

![image](https://github.com/user-attachments/assets/ed803d44-3976-4410-ad49-cbf2c2acb65b)

![image](https://github.com/user-attachments/assets/4eb619ab-6eb7-459a-aa1a-6f3b272fceec)


QUESTION 1 (METHOD 2): LINEAR MODEL USING GRADIENT DESCENT METHOD

![image](https://github.com/user-attachments/assets/4a2adf22-263d-4acf-800d-7c4acee99d1a)

![image](https://github.com/user-attachments/assets/e4cc6839-3e47-4458-8e6e-caaa8a3e0597)

It can be noted that the MSE obtained on train and test data is high and the R-squared value is negative which means the linear model build using gradient descent is not performing well on the given dataset.

QUESTION 2 (METHOD 1): LOGISTIC REGRESSION

Logistic regression is performed when the target variable is categorical but in our case the dependent variable "max_temp" is continuous or numerical so to perform the logistic regression we first need to transform the variable "max_temp" to categorical. Logistic regression can be

i)Binary Classification Logistic Regression

ii)Multinomial Classification Logistic Regression

BINARY CLASSIFICATION

The target variable has only two possible outcomes which is 0 and 1 in our case. To achieve this we first fixed a threshhold value which is half the highest value in the column "max_temp". Then we compare each y-values with the threshold and assign 1 to it if above threshold value and assign 0 to it if less than the threshold. Then we split the data into train and test set and build logistic regression model on it.

![image](https://github.com/user-attachments/assets/a1e565b9-d79d-46dd-935c-470fa660ff9e)

![image](https://github.com/user-attachments/assets/e6763ec4-8d60-4fa2-93b2-1cd52772fa83)

![image](https://github.com/user-attachments/assets/0766d705-8dc6-4b69-b69d-7916a32a7a07)


This shows that the accuracy of the model on test data and train data is almost same, that is, 92%. And the confusion matrix obtained for test data reveals that the False Postive (108) and False Negavtive (119) values are very less indicating a model to be perform well in predicting the target varibale.

MULTINOMIAL CLASSIFICATION LOGISTIC REGRESSION

As said in multinomial logistic regression, the target variable may have more than two possible outcomes. In our case, "max_temp" may be categorised as cold, moderate, or hot temperature. Therefore, again before we could build the model, we convert the "max_temp" variable which is continuous to discrete categories and then use it to build the logistic model. In order to do so,

First we divide the temperature into three categories as cold, moderate and hot.

Secondly, we utilize the library function pd.cut() to set up three bins to store different temperature values and then assign temperature categories to each bins based on their range of temperature values.

![image](https://github.com/user-attachments/assets/11ab8c43-3fc7-4bf1-9e0f-3fe6c7c478c3)

![image](https://github.com/user-attachments/assets/d54e2cac-3460-4651-b375-82b039c099af)




