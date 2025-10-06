# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import pandas and matplot libraries.
2. import Kmeans algorithm to solve customer segmentation.
3. Using the for loop cluster the given data
4. Predict the output and plot data graphs.
5. Display the outputs

## Program:
```

Program to implement the K Means Clustering for Customer Segmentation.
Developed by: ADITYAH M S
RegisterNumber:  212223220002


import pandas as pd
import matplotlib.pyplot as plt
data=pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wess=[]
for i in range(1,11):
  kmeans=KMeans(n_clusters=i,init="k-means++")
  kmeans.fit(data.iloc[:,3:])
  wess.append(kmeans.inertia_)
plt.plot(range(1,11),wess);
plt.xlabel("no of clusters")
plt.ylabel("wess")
plt.title("elbow method")
km=KMeans(n_clusters=5)
km.fit(data.iloc[:,3:])
y_pred=km.predict(data.iloc[:,3:])
data["cluster"]=y_pred
df0=data[data["cluster"]==0]
df1=data[data["cluster"]==1]
df2=data[data["cluster"]==2]
df3=data[data["cluster"]==3]
df4=data[data["cluster"]==4]
plt.scatter(df0["Annual Income"],df0["Score"],c="red",label="cluster0")
plt.scatter(df1["Annual Income"],df1["Score"],c="black",label="cluster1")
plt.scatter(df2["Annual Income"],df2["Score"],c="blue",label="cluster2")
plt.scatter(df3["Annual Income"],df3["Score"],c="green",label="cluster3")
plt.scatter(df4["Annual Income"],df4["Score"],c="red",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
### DATA.HEAD()

<img width="918" height="303" alt="image" src="https://github.com/user-attachments/assets/9d516e96-a4e4-41d3-bf47-42e06d780c6c" />


### DATA.INFO()

<img width="762" height="319" alt="image" src="https://github.com/user-attachments/assets/ef407772-732c-4a93-a3f9-e2a22eba3e0a" />

<img width="1126" height="719" alt="image" src="https://github.com/user-attachments/assets/a599c7c2-a86a-497d-b4ad-b0c671293712" />

<img width="1025" height="578" alt="image" src="https://github.com/user-attachments/assets/d6c3d580-1ef8-4543-bea9-42511db68223" />




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
