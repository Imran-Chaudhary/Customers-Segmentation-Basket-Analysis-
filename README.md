# Customers-Segmentation-Basket-Analysis

In this project I'll be analyzing the dataset of different customers annual spending amounts for diverse product categories. The goal is to best describe the variation of different types of customers that a vendor interects with and how a vendor can improve the services which can help to boost up the revineue. 

### Data Source

The main data source is from Margarida G. M. S. Cardoso, margarida.cardoso '@' iscte.pt, ISCTE-IUL, Lisbon, Portugal, however it can be downloaded from Machine Learning Repository. 

#### Attributes Information

1) FRESH: annual spending (m.u.) on fresh products (Continuous);
2) MILK: annual spending (m.u.) on milk products (Continuous);
3) GROCERY: annual spending (m.u.)on grocery products (Continuous);
4) FROZEN: annual spending (m.u.)on frozen products (Continuous)
5) DETERGENTS_PAPER: annual spending (m.u.) on detergents and paper products (Continuous)
6) DELICATESSEN: annual spending (m.u.)on and delicatessen products (Continuous);
7) CHANNEL: customersâ€™ Channel - Horeca (Hotel/Restaurant/CafÃ©) or Retail channel (Nominal)
8) REGION: customersâ€™ Region â€“ Lisnon, Oporto or Other (Nominal)

## Data Cleaning, Transformation, Exploration and Features Engineering

![text](https://user-images.githubusercontent.com/68614187/106059277-1bb49300-60b8-11eb-9048-ea317a68e7f6.png)

#### Origional Data and Features's Relationship VS Log Transformed Data and Feature's Relationship

1. Non Scaled Data
* Grocery and Detergent show stronger correlation
* Grocery and Milk show slightly stronger correlation
* Detergent_paper and Milk show slightly stronger correlation

2. Logrithmic Scaled Data
* Grocery and Detergent show weeker correlation
* Grocery and Milk show stronger correlation
* Detergent_paper and Milk show slightly stronger correlation

![text](https://user-images.githubusercontent.com/68614187/106059737-c0cf6b80-60b8-11eb-910e-5dc13b0a32c9.png)

![text](https://user-images.githubusercontent.com/68614187/106060485-c24d6380-60b9-11eb-851e-ef6df6b82971.png)

#### Outliers Detection & Removal - Tukey's Method

I applied Tukey's method using 1.5 times of IQR to remove the outliers.

1. Origiona Dataset

![text](https://user-images.githubusercontent.com/68614187/106060975-60412e00-60ba-11eb-8c67-030c3c63e9ab.png)

2. Outliers Removed Dataset

![text](https://user-images.githubusercontent.com/68614187/106061160-9da5bb80-60ba-11eb-9e73-2363120ed79e.png)

#### Dimensionality Reduction and Principal Component Analysis

Once data is cleaned, scaled and transformed to more normal distribution and outliers have been removed. Next step is to see the varience accross all components and chose the numbers contain maximum information.

![text](https://user-images.githubusercontent.com/68614187/106063877-8c5eae00-60be-11eb-9597-cc18c91c0d6f.png)

#### Varience % shown by PCA1 to PCA6

![text](https://user-images.githubusercontent.com/68614187/106064024-c62fb480-60be-11eb-9477-3eaee1f15350.png)

A. 70.68% of the variance in the data is explained by the first and second principal components.
B. 93.11% of the variance in the data is explained by the first four principal components.

PCA 1
* An increase in PC1 is associated with large increases in "Milk", "Grocery" and "Detergents_Paper" spending.
* This is in line with our initial findings where the 3 features are highly correlated.

PCA 2
* An increase in PC2 is associated with large increases in "Fresh", "Frozen" and "Delicatessen" spending.
* This makes sense as PC1 represents different features. And in PC2, the features in PC1 have very small positive weights.

PCA 3
* An increase in PC3 is associated with a large increase in "Delicatessen" and a large decrease in "Fresh" spending.

PCA 4
* An increase in PC4 is associated with a large increasing in "Frozen" and a large decrease in "Delicatessen" spending.

![text](https://user-images.githubusercontent.com/68614187/106063005-2cb3d300-60bd-11eb-9b29-d930a572abed.png)

#### Clustering - Optimal Number of Clusters

Elbow method is used to identify how many clusters I might needed.

![text](https://user-images.githubusercontent.com/68614187/106064454-80272080-60bf-11eb-9513-6473d74e9e70.png)

Average Silhouette score is higher for 2-5 clusters, for both KMeans and GM.

### KMeans Model

* For n_clusters = 2. The average silhouette_score is : 0.42628101546910835
* For n_clusters = 3. The average silhouette_score is : 0.3974234200078323
* For n_clusters = 4. The average silhouette_score is : 0.3316420596309083
* For n_clusters = 5. The average silhouette_score is : 0.352208874352643

![text](https://user-images.githubusercontent.com/68614187/106065215-95507f00-60c0-11eb-9494-2cc5f63cc573.png)


### Gaussian Mixture Model

* For n_clusters = 2. The average silhouette_score is : 0.4219168464626149
* For n_clusters = 3. The average silhouette_score is : 0.37781736386963943
* For n_clusters = 4. The average silhouette_score is : 0.2648661939130228
* For n_clusters = 5. The average silhouette_score is : 0.3377275276519302

![text](https://user-images.githubusercontent.com/68614187/106073353-7c9b9580-60cf-11eb-8a1e-70023725713c.png)

## Conclusion

Since the final data is reduced in dimension and scaled by a logarithm, I recover the representative customer spending from these data points by applying the inverse transformations.

#### Median Values from Original Dataset

* Median values for Fresh: $8504.00
* Median values for Milk: $3627.00
* Median values for Grocery: $4756.00
* Median values for Frozen: $1526.00
* Median values for Detergents_Paper: $816.00
* Median values for Delicassen: $966.00

![text](https://user-images.githubusercontent.com/68614187/106073812-5f1afb80-60d0-11eb-989e-b49ec471dcdb.png)




