# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm Start
1.Start
2.Intialization and Assigning data points to clusters
3.Update centroids
4.Repeat
5.Output

 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Abijith Shaan S
RegisterNumber:212223080002 
*/
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
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
plt.xlabel("No. of clusters")
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
plt.title("Customer Segments")
```

## Output:
Data head:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/98546c47-a754-45eb-8bdf-9da839c94221)

Data info:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/1bf5e4c8-0e1a-49c1-bd45-7534256519d7)

Data isnull().sum():

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/6557eb8a-2600-4c15-8052-933e8d0dc144)

Plotting graph for elbow method:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/f472d1c6-4dbe-4f12-bbd9-66001e113af1)

Y_pred:

![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/7f74ae17-a13a-4ee5-a382-d13c4e2ff369)

Predicting and plotting graph for the clusters:


![image](https://github.com/AkilaMohan/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/160568486/f438730f-33aa-4f50-bbc8-510aacdbbd5a)












## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
