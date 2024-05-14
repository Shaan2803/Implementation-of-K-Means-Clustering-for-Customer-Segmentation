# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import the necessary packages using import statement.

2.Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3.Import KMeans and use for loop to cluster the data.

4.Predict the cluster and plot data graphs.

5.Print the outputs and end the program
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Abijith shaan S
RegisterNumber: 212223080002 
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
  kmeans = KMeans (n_clusters = i, init ="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("no of cluster")
plt.ylabel("wcss")
plt.title("Elbow Metthod")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="blue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="black",label="cluster4")
plt.legend()
```

## Output:
Dataset:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/d277f340-596c-4534-ab71-3bead592efb8)

Dataset information:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/99581d12-cd98-4db9-a59a-5a60d720caf3)

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/3b86a377-e8d0-4f7d-8ffd-f5f90e5ae82f)

Elbow method graph (wcss vs each iteration):

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/876e5c60-cd63-4bc4-b725-d95c48efbdba)

Cluster represnting customer segments-graph:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/ef11cb97-9e8e-4d70-b3f6-4e503cf74b9e)

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
