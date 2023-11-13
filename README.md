# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the necessary packages.
2. Read the given csv file and display the few contents of the data.
3. Import KMeans and use for loop to calculate the within cluster sum of squares the data.
4. Plot the wcss for each iteration, also known as the elbow method plot.
5. Predict the clusters and plot them. 

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: 212221040110
RegisterNumber: NAMITHA.S 
*/
```
```
import pandas as pd
import matplotlib.pyplot as plt
df=pd.read_csv("Mall_Customers.csv")
df.head()
#checking the data information and null presence
df.info()
df.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
   kmeans = KMeans(n_clusters = i,init = "k-means++")
   kmeans.fit(df.iloc[:,3:])
   wcss.append(kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No. of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
plt.show()
km = KMeans(n_clusters = 5)
km.fit(df.iloc[:,3:])
y_pred = km.predict(df.iloc[:,3:])
df["cluster"] = y_pred
df0 = df[df["cluster"]==0]
df1 = df[df["cluster"]==1]
df2 = df[df["cluster"]==2]
df3 = df[df["cluster"]==3]
df4 = df[df["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-
100)"],c="yellow",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-
100)"],c="pink",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-
100)"],c="cyan",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-
100)"],c="skyblue",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-
100)"],c="violet",label="cluster4")
plt.legend()
plt.title("Customer Segments")
plt.show()
```
## Output:
1.data.head()                                                          
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/df7b1b47-4f28-4727-ab26-51e527abe6e4)

2.data.info()            
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/eb3a1121-3058-40a4-811a-e14cf949ef4f)

3.data.isnull().sum()                                                              
4.Elbow method                                          
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/26469f1f-07b0-49a5-9ba7-8b92d5cb64f3)

5. KMeans clusters                                                
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/3cc98cc2-cb8a-40b6-b387-56973c2128bd)

6. array                                                                                                       
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/e38cdde1-78be-476d-ab8b-b76fa3c23614)

7. Customer Segment graph                                                   
![image](https://github.com/NamithaS2710/Implementation-of-K-Means-Clustering-for-Customer-Segmentation/assets/133190822/9a3ca546-6d0d-4628-ac33-16be7077bc01)


## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
