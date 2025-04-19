# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Import the required packages.
2. Import the dataset to work on.
3. From sklearn module import kmeans.
4. Define number of clusters to be made.
5. Assign the cluster values.
6. Plot the cluster using matplotlib.pyplot
7. End the program.

## Program:
```
/*
Program to implement the K Means Clustering for Customer Segmentation.
Developed by: MAHAGAURI P
RegisterNumber:  212224040181
*/
import pandas as pd
import matplotlib.pyplot as plt
data = pd.read_csv("Mall_Customers.csv")
data.head()
data.info()
data.isnull().sum()
from sklearn.cluster import KMeans
wcss = []
for i in range(1,11):
    Kmeans = KMeans(n_clusters = i,init = "k-means++")
    Kmeans.fit(data.iloc[:,3:])
    wcss.append(Kmeans.inertia_)
plt.plot(range(1,11),wcss)
plt.xlabel("No of Clusters")
plt.ylabel("wcss")
plt.title("Elbow Method")
Km = KMeans(n_clusters = 5)
Km.fit(data.iloc[:,3:])
y_pred = Km.predict(data.iloc[:,3:])
y_pred
data["cluster"] = y_pred
df0 = data[data["cluster"]==0]
df1 = data[data["cluster"]==1]
df2 = data[data["cluster"]==2]
df3 = data[data["cluster"]==3]
df4 = data[data["cluster"]==4]
plt.scatter(df0["Annual Income (k$)"],df0["Spending Score (1-100)"],c = "red",label="cluster0")
plt.scatter(df1["Annual Income (k$)"],df1["Spending Score (1-100)"],c = "black",label="cluster1")
plt.scatter(df2["Annual Income (k$)"],df2["Spending Score (1-100)"],c = "blue",label="cluster2")
plt.scatter(df3["Annual Income (k$)"],df3["Spending Score (1-100)"],c = "green",label="cluster3")
plt.scatter(df4["Annual Income (k$)"],df4["Spending Score (1-100)"],c = "magenta",label="cluster4")
plt.legend()
plt.title("Customer Segments")
```

## Output:
![K Means Clustering for Customer Segmentation](sam.png)

### Data Head
![image](https://github.com/user-attachments/assets/3aa1c38c-a77c-47eb-8a96-48e37a62e875)

### Data Information
![image](https://github.com/user-attachments/assets/11011e49-bb16-4bde-add9-439871e422bb)

### Null Data
![image](https://github.com/user-attachments/assets/2f2aa210-b629-4dff-960f-31dbfa4de25e)


### Graph
![image](https://github.com/user-attachments/assets/5a8eb170-eaf1-4c34-a10a-a615fe1ed72a)

### Prediction
![image](https://github.com/user-attachments/assets/90774ead-d49c-4123-acc1-585abf5ee427)

### Customer Graph
![image](https://github.com/user-attachments/assets/0ff99592-c7da-4100-8faa-789ccc918a4a)




## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
