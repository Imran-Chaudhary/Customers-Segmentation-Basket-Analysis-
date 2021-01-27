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

![text](https://user-images.githubusercontent.com/68614187/106062651-b1522180-60bc-11eb-85d2-b2798c60f37d.png)

#### Varience % shown by PCA1 to PCA6

Explained     Variance	Fresh	   Milk	  Grocery	 Frozen	   Detergents_Paper	 Delicassen
  
PComponents 1	 0.4430	  0.1675	-0.4014	 -0.4381	 0.1782	  -0.7514	         -0.1499
PComponents 2	 0.2638	 -0.6859	-0.1672	 -0.0707	-0.5005	  -0.0424        	 -0.4941
PComponents 3	 0.1231	 -0.6774	 0.0402	 -0.0195	 0.3150	  -0.2117	          0.6286
PComponents 4	 0.1012	 -0.2043	 0.0128	  0.0557	 0.7854	   0.2096          -0.5423
PComponents 5	 0.0485	 -0.0026	 0.7192	  0.3554	 -0.0331	-0.5582	         -0.2092
PComponents 6	0.0204	0.0292	-0.5402	0.8205	0.0205	-0.1824	0.0197

![text](https://user-images.githubusercontent.com/68614187/106063005-2cb3d300-60bd-11eb-9b29-d930a572abed.png)

#### Clustering - Optimal Number of Clusters

