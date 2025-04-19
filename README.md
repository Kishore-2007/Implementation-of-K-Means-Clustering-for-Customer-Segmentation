# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages using import statement.

2. Read the given csv file using read_csv() method and print the number of contents to be displayed using df.head().

3. Import KMeans and use for loop to cluster the data.

4. Predict the cluster and plot data graphs.

5. Print the outputs and end the program

## Program:
```PYTHON
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: KISHORE.S 
RegisterNumber: 212224230130 
*/

import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv('Mall_Customers.csv')
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = [] #Within-Cluster Sum of Square.
#It is the sum of squared distance between each point & the centroid in a cluster
for i in range(1,11):
    kmeans = KMeans(n_clusters = i, init = "k-means++")
    kmeans.fit(data.iloc[:, 3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11), wcss)
plt.xlabel("Number of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
km = KMeans(n_clusters = 5)
km.fit(data.iloc[:, 3:])
KMeans(n_clusters = 5)
y_pred = km.predict(data.iloc[:, 3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"] == 0]
df1 = data[data["cluster"] == 1]
df2 = data[data["cluster"] == 2]
df3 = data[data["cluster"] == 3]
df4 = data[data["cluster"] == 4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:

HEAD:

![Screenshot 2025-04-19 224125](https://github.com/user-attachments/assets/e58be48e-26d3-494d-84f5-790150369b26)

INFO:

![Screenshot 2025-04-19 224133](https://github.com/user-attachments/assets/7ef44e24-a857-4a60-a912-ade29ecf7364)

NULL VALUE:

![Screenshot 2025-04-19 224147](https://github.com/user-attachments/assets/3c12c0ec-4973-4ce4-9079-6df9fbf3a6bc)

PLOT:

![Screenshot 2025-04-19 224155](https://github.com/user-attachments/assets/779c4250-f278-4ca7-9137-73fd968a5e40)

CLUSTER VALUE:

![Screenshot 2025-04-19 224202](https://github.com/user-attachments/assets/58a37d07-6967-46b4-9f07-ba2567356ff2)
![Screenshot 2025-04-19 224207](https://github.com/user-attachments/assets/9cdbd66d-f805-4b07-b30b-bbc77598fa1b)

PREDICTED VALUE:

![Screenshot 2025-04-19 224212](https://github.com/user-attachments/assets/a9400100-634e-4ad6-bbcb-d17218900dae)

CLUSTER DATA PLOT:

![Screenshot 2025-04-19 224218](https://github.com/user-attachments/assets/daac2470-821a-4e64-b980-a483cd0bda5d)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
