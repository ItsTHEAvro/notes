# K-Means Clustering
## What is K-Means Clustering?
K-means clustering is a popular unsupervised machine learning algorithm used for grouping unlabeled data points into a predefined number of clusters, denoted by 'k'. The core idea is to partition data into groups such that data points within the same cluster are as similar as possible, and data points in different clusters are as dissimilar as possible.

To create clusters, the K-means clustering algorithm is used, and the Euclidean distance is used to calculate the distance.

## Example 1
| Height | Weight |
|---|---|
| 185 | 72 |
| 170 | 56 |
| 168 | 60 |
| 179 | 68 |
| 182 | 72 |
| 188 | 77 |
| 180 | 71 |
| 180 | 70 |
| 183 | 84 |
| 180 | 88 |
| 180 | 67 |
| 177 | 76 |

The steps of the K-means algorithm are as follows:  
### **Step 0: Input**  
The data points are:  
$
\begin{aligned}
&&P1 = (185, 72)&&\\
&&P2 = (170, 56)&&\\
&&P3 = (168, 60)&&\\
&&P4 = (179, 68)&&\\
&&P5 = (182, 72)&&\\
&&P6 = (188, 77)&&\\
&&P7 = (180, 71)&&\\
&&P8 = (180, 70)&&\\
&&P9 = (183, 84)&&\\
&&P10 = (180, 88)&&\\
&&P11 = (180, 67)&&\\
&&P12 = (177, 76)&&\\
\end{aligned}
$

For this example, $k = 3$ clusters will be used.

### **Step 1: Initialize Centroids**  
Randomly pick 3 initial centroids:
* C1 = P2 = (170, 56) 
* C2 = P6 = (188, 77) 
* C3 = P10 = (180, 88) 

### **Step 2: Assign Points to Nearest Centroid**  
Compute the Euclidean distance of each point to each centroid.  
For P1 = (185, 72):

$
\begin{aligned}
&Distance\ to\ C1:\sqrt{(185 - 170)^2 + (72 - 56)^2} = \sqrt{225 + 256} = \sqrt{481} \approx 21.93&\\
&Distance\ to\ C2:\sqrt{(185 - 188)^2 + (72 - 77)^2} = \sqrt{9 + 25} = \sqrt{34} \approx 5.83&&\\
&Distance\ to\ C3:\sqrt{(185 - 180)^2 + (72 - 88)^2} = \sqrt{25 + 256} = \sqrt{281} \approx 16.76&\\
\end{aligned}
$

P1 is closest to C2.

The approximated distance table and cluster assignments are:

| Point        | C1 (170,56) | C2 (188,77) | C3 (180,88) | Cluster |
| :----------- | :---------- | :---------- | :---------- | :------ |
| P1 (185,72)  | 21.93       | 5.83        | 16.76       | C2      |
| P2 (170,56)  | 0           | 29.83       | 36.80       | C1      |
| P3 (168,60)  | 4.47        | 30.81       | 35.44       | C1      |
| P4 (179,68)  | 13.60       | 11.31       | 20.10       | C2      |
| P5 (182,72)  | 18.87       | 6.71        | 16.28       | C2      |
| P6 (188,77)  | 29.83       | 0           | 15.13       | C2      |
| P7 (180,71)  | 17.03       | 9.49        | 17.00       | C2      |
| P8 (180,70)  | 16.12       | 10.20       | 18.03       | C2      |
| P9 (183,84)  | 33.88       | 7.28        | 5.00        | C3      |
| P10 (180,88) | 36.80       | 15.13       | 0           | C3      |
| P11 (180,67) | 14.87       | 12.04       | 21.47       | C2      |
| P12 (177,76) | 21.63       | 11.18       | 13.00       | C2      |


### **Step 3: Recalculate Centroids**  
New Cluster Assignments are:  
* Cluster 1 (C1): P2, P3 
* Cluster 2 (C2): P1, P4, P5, P6, P7, P8, P11, P12 
* Cluster 3 (C3): P9, P10 

New Centroids are:  
* C1 (mean of P2, P3): $((170 + 168) / 2, (56 + 60) / 2) = (169, 58)$ 
* C2 (mean of 8 points): 

$$X-coord = (185 + 179 + 182 + 188 + 180 + 180 + 180 + 177) / 8 = 181.38$$
$$Y-coord = (72 + 68 + 72 + 77 + 71 + 70 + 67 + 76) / 8 = 71.63$$
$$\rightarrow C2 = (181.38, 71.63)$$


* C3 (P9, P10): $((183 + 180) / 2, (84 + 88) / 2) = (181.5, 86)$ 

### **Step 4: Reassign Points**  
Repeat distance calculation with updated centroids (169, 58), (181.38, 71.63), and (181.5, 86). This process is repeated until centroids do not change significantly.

### **Final Output (after convergence)**  
* Cluster 1: Likely only P2, P3 
* Cluster 2: Majority of middle-range points (e.g., P1, P4–P8, P11–P12) 
* Cluster 3: P9, P10 

## Example 2
| Maths | CS | Result |
|---|---|---|
| 4 | 3 | Fail |
| 6 | 7 | Pass |
| 7 | 8 | Pass |
| 5 | 5 | Fail |
| 8 | 8 | Pass |

The steps of the K-means algorithm are as follows:  
### **Step 0: Input**  
The data points are:  
$
\begin{aligned}
&&P1 = (4, 3)&&\\
&&P2 = (6, 7)&&\\
&&P3 = (7, 8)&&\\
&&P4 = (5, 5)&&\\
&&P5 = (8, 8)&&\\
\end{aligned}
$

For this example, $k = 2$ clusters will be used.

### **Step 1: Initialize Centroids**  
Randomly pick 2 initial centroids:
* C1 = P1 = (4, 3) 
* C2 = P3 = (7, 8) 

### **Step 2: Assign Points to Nearest Centroid**  
Compute the Euclidean distance of each point to each centroid.  
For P1 = (4, 3):

$
\begin{aligned}
&Distance\ to\ C1:\sqrt{(4 - 4)^2 + (3 - 3)^2} = \sqrt{0 + 0} = 0&\\
&Distance\ to\ C2:\sqrt{(4 - 7)^2 + (3 - 8)^2} = \sqrt{9 + 25} = \sqrt{34} \approx 5.83&\\
\end{aligned}
$

P1 is closest to C1.

The approximated distance table and cluster assignments are:

| Point     | C1 (4,3) | C2 (7,8) | Cluster |
| :-------- | :------- | :------- | :------ |
| P1 (4,3)  | 0        | 5.83     | C1      |
| P2 (6,7)  | 4.47     | 1.41     | C2      |
| P3 (7,8)  | 5.83     | 0        | C2      |
| P4 (5,5)  | 2.24     | 3.61     | C1      |
| P5 (8,8)  | 5.66     | 1.00     | C2      |

### **Step 3: Recalculate Centroids**  
New Cluster Assignments are:  
* Cluster 1 (C1): P1, P4 
* Cluster 2 (C2): P2, P3, P5 

New Centroids are:  
* C1 (mean of P1, P4): $((4 + 5) / 2, (3 + 5) / 2) = (4.5, 4)$ 
* C2 (mean of P2, P3, P5): 

$$X-coord = (6 + 7 + 8) / 3 = 7$$
$$Y-coord = (7 + 8 + 8) / 3 = 7.67$$
$$\rightarrow C2 = (7, 7.67)$$

### **Step 4: Reassign Points**  
Repeat distance calculation with updated centroids (4.5, 4) and (7, 7.67):

| Point     | C1 (4.5,4) | C2 (7,7.67) | Cluster |
| :-------- | :--------- | :---------- | :------ |
| P1 (4,3)  | 1.12       | 5.59        | C1      |
| P2 (6,7)  | 3.35       | 1.20        | C2      |
| P3 (7,8)  | 4.72       | 0.33        | C2      |
| P4 (5,5)  | 1.12       | 2.92        | C1      |
| P5 (8,8)  | 4.72       | 1.04        | C2      |

The cluster assignments remain the same, so the algorithm has converged.

### **Final Output (after convergence)**  
* Cluster 1: P1(4,3), P4(5,5) - Students with lower scores (Fail)
* Cluster 2: P2(6,7), P3(7,8), P5(8,8) - Students with higher scores (Pass)

Final Centroids:
* C1 = (4.5, 4) - Center of "Fail" group
* C2 = (7, 7.67) - Center of "Pass" group