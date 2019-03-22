# PySpark_KmeansClustering
K-means clustering on an e-commerce dataset with PySpark


We first load all datasets that are going to be used with spark.read.csv and then join them one by one and remove all NAs along the way. 
We had 111,686 rows of data after cleaning.
The chosen features are the 3 numeric variables including survey_score, price, product_photos_qty. No categorical variables are applicable because the distance function in k-means is Euclidean Distance, and even though some discussions mentioned k-mode to be a possible alternative for categorical variables, we did not proceed because we are more interested in what results these variables with k-means clustering would give us. 
In the EDA part, we could see there is no correlation between variables so we were good to proceed with the analysis without concerns of skewness.

In terms of model building, we did 75-25 split for training and testing datasets and standardized the scales. 
According to the elbow plot, k=5 is the most ideal size because it’s the point where the diminishing returns of adding more clusters kicked in. 
With k=5, the training and testing clusters had very similar results, meaning there was no obvious signs of overfitting or underfitting of our model.

Based on the resulting centroid prediction and cluster plot, we can see the biggest cluster is the No.1 cluster in the red line with the highest survey score and normal price level as well as relatively lower picture quantity. 
The smallest cluster is the No. 2 cluster in the green line with the significantly higher price and normal level of survey score and picture quantity. 
If higher-priced products can lead to more profit to the company, it would be recommended to increase the number of higher-priced products featured in cluster No.2. 
There is a group of obviously lower-rated products featured in cluster No.0 that would be worthy of further investigation with other additional numeric features to make systematic improvements.
