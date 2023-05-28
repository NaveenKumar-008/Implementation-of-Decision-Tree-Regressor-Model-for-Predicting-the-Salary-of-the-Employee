# Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee

## AIM:
To write a program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required libraries.
2. Upload the csv file and read the dataset.
3. Check for any null values using the isnull() function.
4. From sklearn.tree import DecisionTreeRegressor.
5. Import metrics and calculate the Mean squared error.
6. Apply metrics to the dataset, and predict the output.


## Program:
```
/*
Program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee.
Developed by: NAVEEN KUMAR M  
RegisterNumber:  212221040113
*/
```

```
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
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/4e7b07fc-0017-4fab-aaeb-b18533dc6450)

## data.info()
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/4d068f16-31fa-4c00-bf45-cdbc2b8c2836)

## isnull() and sum()
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/0b5838c6-cbf1-4a14-a6bc-d8ccaa960a0f)

## data.head() for position
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/b793a45c-34f2-439b-afc8-f37aafa74c5a)

## MSE value
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/b834b0d1-a426-4815-9c76-862074add2d1)

## r2 value
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/8527fc96-726f-4536-b9d2-acd0a16a11a6)

## data prediction
![image](https://github.com/NaveenKumar-008/Implementation-of-Decision-Tree-Regressor-Model-for-Predicting-the-Salary-of-the-Employee/assets/128135244/4cc201d7-96e2-459e-9f63-13c627dd6704)

## Result:
Thus the program to implement the Decision Tree Regressor Model for Predicting the Salary of the Employee is written and verified using python programming.
