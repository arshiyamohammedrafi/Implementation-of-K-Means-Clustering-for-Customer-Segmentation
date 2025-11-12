# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Load and preprocess data: Import data, inspect it, and handle missing values if any.

2.Determine optimal clusters: Use the Elbow Method to identify the number of clusters by plotting WCSS against cluster numbers.

3.Fit the K-Means model: Apply K-Means with the chosen number of clusters to the selected features.

4.Assign cluster labels to each data point.

5.Plot data points in a scatter plot, color-coded by cluster assignments for interpretation.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ARSHIYA M
RegisterNumber: 212224040029 
*/
```
```


import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters=i,init= "k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No_of_Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred = km.predict(data.iloc[:,3:])
y_pred
data["cluster"]=y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="blue",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="green",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="yellow",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="purple",label="cluster4")
plt.legend()
plt.figure("Customer Segements")
```
## Output:

<img width="1235" height="217" alt="499154902-da04006e-7c14-4c37-8109-999c17ea620c" src="https://github.com/user-attachments/assets/a8132572-2b4c-4762-90bd-6cdd26b56342" />

<img width="1221" height="284" alt="499155009-c41aad46-5493-4707-95cc-8c3c2547d878" src="https://github.com/user-attachments/assets/07b67d41-4ac5-4ef6-96a8-017e69b8fc19" />

<img width="1244" height="160" alt="499155065-85b3fe5f-dd6d-49f2-84d1-e177f461a5e4" src="https://github.com/user-attachments/assets/28f2a2c5-a08c-4f50-894e-e165953ac695" />

<img width="1243" height="626" alt="499155140-5a02e239-c7b8-4031-9e18-83f713edf0b8" src="https://github.com/user-attachments/assets/1e9fdb7a-889c-4f0d-934b-56a8e87142c1" />

<img width="1229" height="107" alt="499155209-d84e69de-ff16-42e5-9c67-a8c8ee0afd45" src="https://github.com/user-attachments/assets/b754992c-b6d6-4608-ae14-2c734712afa1" />

<img width="1270" height="231" alt="499155301-42e79d66-5c36-4893-bfe3-074243ac17d5" src="https://github.com/user-attachments/assets/5e181a57-5d59-4b40-bcc4-e74c8ad668f0" />

<img width="1249" height="591" alt="499155387-c9046310-999c-4c19-a474-25c6b3bbc515" src="https://github.com/user-attachments/assets/459c0abd-a8c2-4f9a-8d7d-21d1e9b4ff6e" />
## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
