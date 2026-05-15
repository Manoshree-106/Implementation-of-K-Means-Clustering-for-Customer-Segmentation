# Implementation-of-K-Means-Clustering-for-Customer-Segmentation

## AIM:
To write a program to implement the K Means Clustering for Customer Segmentation.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Jupyter notebook

## Algorithm
1. Get the independent variable X and dependent variable Y.
2. Calculate the mean of the X -values and the mean of the Y -values.
3. Find the slope m of the line of best fit using the formula.
  <img width="350" height="192" alt="Screenshot 2026-05-11 093010" src="https://github.com/user-attachments/assets/5fb63f44-9a7f-45ae-b101-a63ae350be21" />

4. commpute the y -intercept of the line by using the formula:
<img width="312" height="62" alt="Screenshot 2026-05-11 093018" src="https://github.com/user-attachments/assets/50a460be-e8f7-4f04-a7a4-3b2c9658b4dd" />


5.Use the slope m and the y -intercept to form the equation of the line. 
6. Obtain the straight line equation Y=mX+b and plot the scatterplot.

## Program:
```
/*
Developed by: MANOSHREE N
RegisterNumber:  212225040228
# Import libraries
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# ------------------------------
# Step 1: Sample dataset
# ------------------------------
data = {
    'CustomerID': [1,2,3,4,5,6,7,8,9,10],
    'Gender': ['Male','Female','Female','Male','Female','Male','Male','Female','Female','Male'],
    'Age': [19,21,20,23,31,22,35,30,25,28],
    'Annual Income (k$)': [15,16,17,18,19,20,21,22,23,24],
    'Spending Score (1-100)': [39,81,6,77,40,76,6,94,3,72]
}

df = pd.DataFrame(data)

# ------------------------------
# Step 2: Select features for clustering
# ------------------------------
X = df[['Annual Income (k$)', 'Spending Score (1-100)']]

# ------------------------------
# Step 3: Apply K-Means (choose clusters, e.g., 3)
# ------------------------------
kmeans = KMeans(n_clusters=3, init='k-means++', random_state=42)
df['Cluster'] = kmeans.fit_predict(X)  # Automatically fits and assigns clusters

# ------------------------------
# Step 4: Visualize clusters
# ------------------------------
plt.figure(figsize=(8,6))
for i in range(3):
    plt.scatter(X[df['Cluster']==i]['Annual Income (k$)'],
                X[df['Cluster']==i]['Spending Score (1-100)'],
                label=f'Cluster {i+1}')

# Plot centroids
plt.scatter(kmeans.cluster_centers_[:,0], kmeans.cluster_centers_[:,1],
            s=200, c='yellow', label='Centroids', marker='X')

plt.title('Customer Segmentation (K-Means)')
plt.xlabel('Annual Income (k$)')
plt.ylabel('Spending Score (1-100)')
plt.legend()
plt.show()

# ------------------------------
# Step 5: Show dataset with clusters
# ------------------------------
print(df)

*/
```

## Output:
<img width="947" height="661" alt="Screenshot 2026-05-15 173505" src="https://github.com/user-attachments/assets/47fda508-ac23-43da-9cf9-debba8a3535b" />
<img width="766" height="543" alt="Screenshot 2026-05-15 173519" src="https://github.com/user-attachments/assets/34743854-3a57-4038-9d2c-754a96f64acf" />



## Result:
Thus the program to implement the K Means Clustering for Customer Segmentation is written and verified using python programming.
