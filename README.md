# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1)Import the necessary packages using import statement.
2)Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().
3)Import KMeans and use for loop to cluster the data.
4)Predict the cluster and plot data graphs.
5)Print the outputs and end the program


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: BALAJEE K.S
RegisterNumber:  212222080009

*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("/content/Mall_Customers (1).csv")

data.head()

data.isnull().sum()

from sklearn.cluster import KMeans
wcss=[]

for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No.of clusters")
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
![K Means Clustering for Customer Segmentation](sam.png)

data.head():

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/cc2fe737-f9c8-4243-ac24-50e4c3034692)

data.info():

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/c3e6f8d8-7eed-47eb-b51f-aa6133553249)

data.isnull().sum():

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/6b5ba726-c449-46d8-9cdf-03b4cd15f572)

Elbow method graph:

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/7ecdcc2c-a843-45dd-97e6-c22b62a7de96)


KMeans clusters:

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/4df05173-c26d-4bb8-a6ae-09f2a6720ced)

y_pred:

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/e463ab30-9c69-43fa-81c7-dfeeb0c25e93)


Customers Segments Graph:

![image](https://github.com/balajeeakm/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/131589871/fde8ffd4-30a3-466a-a633-4fa6f49c1890)














## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
