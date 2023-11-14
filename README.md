# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the required libraries.

2.Upload the csv file and read the dataset.

3.Check for any null values using the isnull() function.

4.From sklearn.tree import DecisionTreeRegressor.

5.Import metrics and calculate the Mean squared error.

6.Apply metrics to the dataset, and predict the output.

## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: s.monicka
RegisterNumber: 212221220033 
*/
import pandas as pd
data=pd.read_csv("/content/Salary.csv")

print("data.head():")
data.head()

print("data.info():")
data.info()

print("isnull() and sum():")
data.isnull().sum()

from sklearn.preprocessing import LabelEncoder
le=LabelEncoder()
data["Position"]=le.fit_transform(data["Position"])
print("data.head() for salary:")
data.head()

x=data[["Position","Level"]]
y=data["Salary"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test=train_test_split(x,y,test_size=0.2,random_state=2)

from sklearn.tree import DecisionTreeRegressor
dt=DecisionTreeRegressor()
dt.fit(x_train,y_train)
y_pred=dt.predict(x_test)

from sklearn import metrics
mse=metrics.mean_squared_error(y_test,y_pred)
print("MSE value:")
mse

r2=metrics.r2_score(y_test,y_pred)
print("r2 value:")
r2

print("data prediction:")
dt.predict([[5,6]])
```
## Output:
## data.head()
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/2da9b18b-7620-402e-b045-bf4b18ce5180)
## data info()
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/160d74be-2eed-4623-97f4-14348b0d48e8)
## isnull() and sum() function
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/eb751692-53f7-429b-ac4f-67e1d6887a31)
## data.head() for salary
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/70720ba7-7ac2-4e93-8bf4-79d889e83045)
## MSE Value
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/fa6a3114-674e-4213-99a0-3c48c73150ab)
## R2 value
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/e7dbb9fb-823c-4e99-9ce4-bb4726efd44c)
## Prediction value
![image](https://github.com/Monicka19/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/143497806/e0d97cdf-d037-47bc-8cce-7df76b682a0c)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
