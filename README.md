# Implementation-of-Decision-Tree-Classifier-Model-for-Predicting-Employee-Churn

## AIM:
To write a program to implement the Decision Tree Classifier Model for Predicting Employee Churn.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas module and import the required data set.
2. Find the null values and count them.
3. Count number of left values.
4. From sklearn import LabelEncoder to convert string values to numerical values.
5. From sklearn.model_selection import train_test_split.
6. Assign the train dataset and test dataset.
7. From sklearn.tree import DecisionTreeClassifier.
8. Use criteria as entropy.
9. From sklearn import metrics.
10. Find the accuracy of our model and predict the require values. 
## Program:
```
/*
Program to implement the Decision Tree Classifier Model for Predicting Employee Churn.
Developed by: Sangeetha S
RegisterNumber: 212224040287 
*/
import pandas as pd
data = pd.read_csv("Employee.csv")
data.head()
data.info()

data.isnull().sum()

data["left"].value_counts

from sklearn.preprocessing import LabelEncoder
le= LabelEncoder()
data["salary"]=le.fit_transform(data["salary"])
data.head()

x= data[["satisfaction_level","last_evaluation","number_project","average_montly_hours","time_spend_company","Work_accident","promotion_last_5years","salary"]]

x.head()
y=data["left"]

from sklearn.model_selection import train_test_split
x_train,x_test,y_train,y_test = train_test_split(x,y,test_size=0.2,random_state = 100)

from sklearn.tree import DecisionTreeClassifier
dt = DecisionTreeClassifier(criterion="entropy")
dt.fit(x_train,y_train)

y_pred = dt.predict(x_test)
from sklearn import metrics

accuracy = metrics.accuracy_score(y_test,y_pred)
accuracy

dt.predict([[0.5,0.8,9,260,6,0,1,2]])
```

## Output:
<img width="1355" height="296" alt="Screenshot 2025-10-24 052935" src="https://github.com/user-attachments/assets/986e07e4-0afe-4257-8f5a-0b83af268fc6" />
<img width="940" height="350" alt="Screenshot 2025-10-24 052941" src="https://github.com/user-attachments/assets/94152783-1c29-44ac-b69a-dc63114d0668" />
<img width="937" height="453" alt="Screenshot 2025-10-24 052949" src="https://github.com/user-attachments/assets/7aea33f4-1ba8-4658-a4f1-1ef75e4c2dcd" />
<img width="861" height="230" alt="Screenshot 2025-10-24 052955" src="https://github.com/user-attachments/assets/b5bf06c5-2d96-47cc-8580-a6d806028e9c" />
<img width="1369" height="349" alt="Screenshot 2025-10-24 053004" src="https://github.com/user-attachments/assets/67af24d4-5d01-4198-977a-02f46a4fb4b3" />
<img width="1291" height="299" alt="Screenshot 2025-10-24 053011" src="https://github.com/user-attachments/assets/925a712c-7269-4663-b493-a7955d2bb870" />
<img width="947" height="233" alt="Screenshot 2025-10-24 053016" src="https://github.com/user-attachments/assets/b0341503-3ebe-4786-bf68-aa6e89431f3c" />
<img width="597" height="151" alt="Screenshot 2025-10-24 053021" src="https://github.com/user-attachments/assets/dd1a4f1f-b83a-41c2-9f87-332efa6fa1d4" />
<img width="1441" height="111" alt="Screenshot 2025-10-24 053239" src="https://github.com/user-attachments/assets/ab0c2929-a889-4900-b830-26315f151eb0" />




## Result:
Thus the program to implement the  Decision Tree Classifier Model for Predicting Employee Churn is written and verified using python programming.
