# Chapter 14. Clustering

Partitioning of a set of objects into groups or clusters. It can be used for EDA, or generalization. Clustering algorithms can perform soft  clustering or hard clustering.

In a vector space model, degree of membership in multiple clusters can be formalized as the similarity of a vector to the center of each cluster (centroid or center of gravity).

In hierarchical clustering, assignment is usually hard, in non-hierarchical clustering (k-means, EM algorithm) both types are common. K-means can't be used for many datasets, nominal data (colors). EM algorithm can accommodate this.

## 14.1. Hierarchical clustering

The tree of a hierarchical clustering can be built bottom up (agglomerative clustering) or top-down (divisive clustering).

* single-link: similarity of the two most similar members
* complete-link: similarity of the two least similar members
* group-average: average similarity between members

### 14.1.1. Single-link and complete-link clustering

The similarity function determines which clusters are merged in each step. In single-link clustering(O(n^2)) the similarity between two clusters is the similarity of the two closest objects in the clusters. Single-link clusterings have clusters with good local coherence because the similarity function is locally defined, but the clusters can be elongated. 

Clusters in single-link can be locally coherent, meaning that close objects are in the same cluster, but can have bad global quality. one point at the border might be closer to another point at the border of another cluster

Complete-link clustering(O(n^2 logn)) focuses on global cluster quality. 

### 14.1.2. group-average agglomerative clustering

p507-509

### 14.1.3. An application: improving a language model

Clustering can play an important role in improving the language model by way of generalization, when we don't have enough training data for accurate probabilistic modelling. More on the language model and clustering formulas in p510-512.

### 14.1.4. Top-down clustering

512-514

## 14.2. Non-hierarchical clustering

They start out with a partition based on randomly selected seeds (one seed per cluster), and then refine this initial partition. They employ several passes of reallocating objects to the currently best cluster, whereas hierarchical algorithms need only one pass. The passes stop based on a measure of goodness or cluster quality. And how do we determine the right number of clusters?

### 14.2.1. K-means

Hard clustering algorithm that defines clusters by the center of mass of their members. At the beginning we need a set of initial cluster centers. Then there are several iterations of first assigning each object to the cluster whose center is closest and then recomputing the center of each cluster as centroid or mean of it.

K-mean is sensitive to outliers --> k-medoid, where one point is chosen as cluster center. 

### 14.2.2. The EM algorithm

'soft' version of k-means. we start with a set of random cluster centers. the EM algorithm does a soft assignment at first. The EM algorithm can be used for the estimation of Gaussian mixtures. More on Gaussian distribution in p519-524.

It's very sensible to the initialization of its parameters, and if they're not initialized well, the algorithm gets stuck in one of the many local maxima. The rate of convergence of the EM can be very slow
