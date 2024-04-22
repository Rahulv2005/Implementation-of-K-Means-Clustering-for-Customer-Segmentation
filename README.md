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
Developed by:RAGHUL V
RegisterNumber: 212223240132 
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
![image](https://github.com/Rahulv2005/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152600335/382fe7e5-1164-479a-8f12-33cdd81f4005)
![image](https://github.com/Rahulv2005/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152600335/264d1b1d-c043-4a3f-ad2b-9d0ebc65710e)
![image](https://github.com/Rahulv2005/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152600335/03978b3e-035f-4ecb-94d3-4add5cf85054)
![image](https://github.com/Rahulv2005/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/152600335/e781d71e-a424-4879-aaaf-d252ee6e6b10)



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
