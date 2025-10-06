# Implementation-of-K-Means-Clustering-for-Customer-Segmentation
## Name: Renick Fabian Rajesh
## Reg No: 212224230227
## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import dataset and print head,info of the dataset
2. check for null values
3. Import kmeans and fit it to the dataset
4. Plot the graph using elbow method
5. Print the predicted array
6. Plot the customer segments

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: Renick Fabian Rajesh
RegisterNumber: 212224230227 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("Mall_Customers.csv")
df.head()
df.info()
df.isnull().sum()
from sklearn.cluster import KMeans
wcss=[] 
for i in range (1,11):
    kmeans=KMeans(n_clusters=i,init="k-means++")
    kmeans.fit(df.iloc[:,3:])
    wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow method")
km=KMeans(n_clusters=5)
km.fit(df.iloc[:,3:])
KMeans(n_clusters=5)
y_pred=km.predict(df.iloc[:,3:])
y_pred
df["cluster"]=y_pred
df0=df[df["cluster"]==0]
df1=df[df["cluster"]==1]
df2=df[df["cluster"]==2]
df3=df[df["cluster"]==3]
df4=df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c="red",label="clsuter0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c="black",label="clsuter1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c="blue",label="clsuter2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c="green",label="clsuter3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c="yellow",label="clsuter4")
plt.legend()
plt.title("Customer Segments")

```

## Output:
<img width="703" height="254" alt="image" src="https://github.com/user-attachments/assets/29e4eee7-8ba7-4496-8a98-0f88da2ad753" />
<img width="529" height="251" alt="image" src="https://github.com/user-attachments/assets/73691d78-acee-489d-b59d-f9fea33bf64b" />
<img width="258" height="285" alt="image" src="https://github.com/user-attachments/assets/ec914244-dbc2-4385-a0a9-1b467c331ff2" />
<img width="749" height="571" alt="image" src="https://github.com/user-attachments/assets/5a5b9fbf-f7c0-4f6c-8c01-87b6275d2bba" />
<img width="692" height="541" alt="image" src="https://github.com/user-attachments/assets/5450d8d2-ac7e-4353-85c8-c3258a579004" />





## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
