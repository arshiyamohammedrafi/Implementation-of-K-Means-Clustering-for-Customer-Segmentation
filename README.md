







# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1.Import dataset and print head,info of the dataset

2.Check for null values

3.Import kmeans and fit it to the dataset

4.Plot the graph using elbow method

5.Print the predicted array

6.Plot the customer segments

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.

Developed by: ARSHIYA M
RegisterNumber: 212224040029 

```
```
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Load dataset
data = pd.read_csv("Mall_Customers.csv")

# Basic info
print(data.head())
print(data.info())

# Implementation-of-KMeans-Clustering-for-Customer-Segmentation/README.md at main · Deepikaasuresh304/Implementation-of-KMeans-Clustering-for-Customer-Segmentation/blob/main/README.md
print(data.isnull().sum())

# Elbow method to find optimal number of clusters
wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init="k-means++", random_state=42)
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)

# Plot the elbow curve
plt.plot(range(1, 11), wcss, marker='o')
plt.xlabel("Number of Clusters")
plt.ylabel("WCSS")
plt.title("Elbow Method")
plt.grid(True)
plt.show()

# Apply KMeans with 5 clusters
km = KMeans(n_clusters=5, init="k-means++", random_state=42)
y_pred = km.fit_predict(data.iloc[:, 3:])

# Add cluster label to the data
data["cluster"] = y_pred

# Separate the clusters
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]

# Visualize the clusters
plt.scatter(df0["Annual Income (k$)"], df0["Spending Score (1-100)"], c="red", label="Cluster 0")
plt.scatter(df1["Annual Income (k$)"], df1["Spending Score (1-100)"], c="black", label="Cluster 1")
plt.scatter(df2["Annual Income (k$)"], df2["Spending Score (1-100)"], c="blue", label="Cluster 2")
plt.scatter(df3["Annual Income (k$)"], df3["Spending Score (1-100)"], c="green", label="Cluster 3")
plt.scatter(df4["Annual Income (k$)"], df4["Spending Score (1-100)"], c="magenta", label="Cluster 4")

plt.title("Customer Segments")
plt.xlabel("Annual Income (k$)")
plt.ylabel("Spending Score (1-100)")
plt.legend()
plt.grid(True)
plt.show()
```

## Output:

<img width="804" height="534" alt="Screenshot 2025-10-06 111546" src="https://github.com/user-attachments/assets/ebb43fb0-1f08-4610-ab0a-f63cceb357b5" />

<img width="828" height="557" alt="Screenshot 2025-10-06 111602" src="https://github.com/user-attachments/assets/5f829141-2887-4b21-b9fd-aa6d6e2b6832" />

<img width="920" height="616" alt="Screenshot 2025-10-06 111621" src="https://github.com/user-attachments/assets/191a9eb9-b952-4f0c-a07f-224183eefdee" />






## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
