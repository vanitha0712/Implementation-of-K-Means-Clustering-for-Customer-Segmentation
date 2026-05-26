# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Load the customer dataset and select the relevant features such as Annual Income and Spending Score.
2.Choose the number of clusters K and initialize K centroids randomly
3.Assign each data point to the nearest centroid using Euclidean distance and update the centroids by calculating the mean of each cluster.
4.Repeat Step 3 until the centroids no longer change and display the final clusters for customer segmentation.
## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: B.VANITHA
RegisterNumber: 212225220117
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

data = pd.read_csv("C:/Users/Sushmitha/Downloads/Mall_Customers.csv")
print(data.head())

X = data.iloc[:, [3, 4]].values

wcss = []
for i in range(1, 11):
    kmeans = KMeans(n_clusters=i, init='k-means++', random_state=42)
    kmeans.fit(X)
    wcss.append(kmeans.inertia_)
    
plt.figure(figsize=(8,5))
plt.plot(range(1, 11), wcss, marker='o')
plt.title('Elbow Method')
plt.xlabel('Number of Clusters')
plt.ylabel('WCSS')
plt.show()

kmeans = KMeans(n_clusters=5, init='k-means++', random_state=42)
y_kmeans = kmeans.fit_predict(X)
plt.figure(figsize=(8,6))
plt.scatter(X[y_kmeans == 0, 0], X[y_kmeans == 0, 1], s=100, c='red', label='Cluster 1')
plt.scatter(X[y_kmeans == 1, 0], X[y_kmeans == 1, 1], s=100, c='blue', label='Cluster 2')
plt.scatter(X[y_kmeans == 2, 0], X[y_kmeans == 2, 1], s=100, c='green', label='Cluster 3')
plt.scatter(X[y_kmeans == 3, 0], X[y_kmeans == 3, 1], s=100, c='cyan', label='Cluster 4')
plt.scatter(X[y_kmeans == 4, 0], X[y_kmeans == 4, 1], s=100, c='magenta', label='Cluster 5')

plt.scatter(kmeans.cluster_centers_[:,0], 
            kmeans.cluster_centers_[:,1], 
            s=300, c='yellow', label='Centroids')

plt.title('Customer Segmentation using K-Means')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()

*/
```

## Output:
<img width="1071" height="201" alt="Screenshot 2026-05-26 085930" src="https://github.com/user-attachments/assets/56163003-69df-4928-8e86-c3e75961844b" />
<img width="1098" height="493" alt="Screenshot 2026-05-26 085949" src="https://github.com/user-attachments/assets/af35e6ec-2203-435a-bbb4-682b7313e1c8" />
<img width="1026" height="573" alt="Screenshot 2026-05-26 090003" src="https://github.com/user-attachments/assets/f32ed7d9-6983-4f45-bbf5-635f3358be41" />

## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
