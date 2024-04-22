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
'''
Program to implement the K Means Clustering for Customer Segmentation.
Developed by : K MADHAVA REDDY
RegisterNumber : 212223240064  
'''
import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv(r'Mall_Customers.csv')

data.head()
data.info()
data.isnull().sum()

from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    kmeans = KMeans(n_clusters = i,init = "k-means++")
    kmeans.fit(data.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")

km = KMeans(n_clusters = 5)
km.fit(data.iloc[:,3:])

y_pred = km.predict(data.iloc[:,3:])
y_pred

data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### Head()
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/12e02ae0-06e5-47c0-a26e-d4e582b2f200)

### Info()
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/b70f48a7-3734-42bf-ae03-6f8890dd28f0)

### isnull.sum()
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/8a431583-dcbf-4311-9bd4-39dc5af03c41)

### Elbow Method
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/9efa8505-3589-490d-8980-8a3e62073153)

### Fitting the no. of clusters
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/7eae3f79-61eb-4aff-9bad-6fa849eaca41)

### Prediction of Y
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/ed33ffde-d901-4bdb-ab3a-a5e6bdb7f958)

### Customer Segments
![image](https://github.com/Madhavareddy09/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/145742470/3bb7eca9-7b85-4086-ab1b-fb37589a6fcd)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
