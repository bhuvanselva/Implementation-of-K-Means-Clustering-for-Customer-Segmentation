# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import pandas and matplotlib.pyplot

2. Read the dataset and transform it

3. Import KMeans and fit the data in the model

4. Plot the Cluster graph 


## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: BHUVANESHWARI S
RegisterNumber:  212222220008
*/
```


```
import pandas as pd
import matplotlib.pyplot as plt

data = pd.read_csv(r"C:\Users\admin\Downloads\Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []

for i in range(1,11):
    kmeans = KMeans(n_clusters=i, init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)

plt.plot(range(1,11),wcss)
plt.xlabel("No. of clusters")
plt.ylabel("wcss")
plt.title("Elbow method")

km = KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred

df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster 0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster 1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster 2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster 3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster 4")

plt.legend()
plt.title("customer segmentation")
```
# Output:

![image](https://github.com/user-attachments/assets/b25dd3fa-4f7e-4aa3-8dae-57f8957972d4)

![image](https://github.com/user-attachments/assets/83fdd7db-9909-48f3-a7d3-2463aab12896)

![image](https://github.com/user-attachments/assets/8616e65f-4b98-4070-92ea-d3b4fcd31e58)

![image](https://github.com/user-attachments/assets/3a86fe56-0961-47e4-a4dd-105ca3678bcb)

![image](https://github.com/user-attachments/assets/fdf9fb6d-6276-4b82-afd1-fd4559008178)

![image](https://github.com/user-attachments/assets/77622b32-0d12-4966-afd7-ce401f4c8699)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
