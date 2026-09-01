### EX4 Implementation of Cluster and Visitor Segmentation for Navigation patterns
### DATE: 17-08-2026
### AIM: To implement Cluster and Visitor Segmentation for Navigation patterns in Python.
### Description:
<div align= "justify">Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website, 
  application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit. 
  This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts, 
  or services to meet the specific needs and preferences of each cluster.</div>
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.

### Program:
```python
import pandas as pd
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

df = pd.read_csv("clustervisitor.csv")

X = df[['Age']]

kmeans = KMeans(n_clusters=3, random_state=42)

df['Cluster'] = kmeans.fit_predict(X)

print(df)

for i in range(3):
    print(f"\nCluster {i}")
    print(df[df['Cluster'] == i])

```
### Output:


<img width="434" height="527" alt="image" src="https://github.com/user-attachments/assets/73634ef8-68b7-42cb-819b-719129fc61a1" />



<img width="419" height="231" alt="image" src="https://github.com/user-attachments/assets/b125ed52-4f3c-4276-9a3d-330940cf8be6" />


<img width="421" height="217" alt="image" src="https://github.com/user-attachments/assets/201318d2-c061-43a5-b014-7d49f0e5c0c3" />


<img width="400" height="196" alt="image" src="https://github.com/user-attachments/assets/b473e619-0f9e-46f5-a37c-a630d737da5a" />




### Visualization:
```python
import matplotlib.pyplot as plt

plt.figure(figsize=(8,5))

for i in range(3):
    cluster = df[df['Cluster'] == i]
    plt.scatter(cluster['Age'], cluster['Cluster'], label=f'Cluster {i}')

plt.scatter(
    kmeans.cluster_centers_,
    range(3),
    color='red',
    marker='X',
    s=200,
    label='Centroids'
)

plt.xlabel("Age")
plt.ylabel("Cluster")
plt.title("Visitor Segmentation using K-Means")
plt.legend()
plt.grid(True)
plt.show()
```
### Output:


<img width="692" height="448" alt="image" src="https://github.com/user-attachments/assets/8f43b5a8-88d7-445a-8884-583984472c0a" />



### Result:
Thus the code has been executed successfully.


