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
Developed by: Abijith Shaan S 
RegisterNumber: 212223080002
*/
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: SASIDHARAN P
RegisterNumber:  212223080051
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
plt.title("Customer Segments")
```

## Output:
Dataset:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/dd612e83-7548-43da-b1a4-a9c7877ca63e)

Dataset information:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/d55de05c-63de-4750-8800-9d2ca1d098c4)

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/1f79f6dd-f2c2-40a2-a42c-55288ed89f64)

Elbow method graph (wcss vs each iteration):


![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/1d3a7068-9f1d-420d-832d-0c087d76ea2a)

Cluster represnting customer segments-graph:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/8dae3518-d2a3-4250-bb98-f34c31e59fa7)






## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
