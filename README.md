# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. 1.Import dataset and print head,info of the dataset

2.check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Nandhini.S
RegisterNumber: 212224230174
*/
```
```

import pandas as pd

import matplotlib.pyplot as plt

data=pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.info()

data.isnull().sum()

from sklearn.cluster import KMeans

wcss=[]

for i in range(1,11):

kmeans=KMeans(n_clusters=i,init="k-means++")

kmeans.fit(data.iloc[:,3:])

wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)

plt.xlabel("No_of_Clusters")

plt.ylabel("wcss")

plt.title("Elbow Method")

km=KMeans(n_clusters=5)

km.fit(data.iloc[:,3:])

y_pred=km.predict(data.iloc[:,3:])

y_pred

data["cluster"]=y_pred

df0=data[data["cluster"]==0]

df1=data[data["cluster"]==1]

df2=data[data["cluster"]==2]

df3=data[data["cluster"]==3]

df4=data[data["cluster"]==4]

plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")

plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")

plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")

plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")

plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")

plt.legend()

plt.title("Customer Segment")
```
## Output:
1.DATA.HEAD():

![image](https://github.com/user-attachments/assets/59c7b1df-7551-410d-ad61-585f0305d26b)

2.DATA.INF0():

![Screenshot 2025-05-07 012642](https://github.com/user-attachments/assets/2ba4a2d8-5eb6-478a-94dc-6ea150f10268)

3.DATA.ISNULL().SUM():

![Screenshot 2025-05-07 012721](https://github.com/user-attachments/assets/aac5c35b-ee30-4634-93ba-d46799362ab6)

4.PLOT USING ELBOW METHOD:

![Screenshot 2025-05-07 012759](https://github.com/user-attachments/assets/55069782-954f-4a52-8269-260d915c028a)

5.K-MEANS CLUSTERING:

![Screenshot 2025-05-07 012839](https://github.com/user-attachments/assets/87a8793a-f44e-4f18-8849-2e0980b26754)

6.Y_PRED ARRAY:

![Screenshot 2025-05-07 012918](https://github.com/user-attachments/assets/b3cca543-91e4-4935-b4b8-0b0a256b5c0b)

7.CUSTOMER SEGMENT:

![Screenshot 2025-05-07 013005](https://github.com/user-attachments/assets/ea72185c-d5f8-429f-857e-2bdf8a973b3c)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
