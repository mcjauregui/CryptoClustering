# CryptoClustering

In this challenge, you’ll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.   

As can be seen in the file Crypto_Clustering.ipynb, the data set is made up of 41 rows (cryptocurrencies) and 7 columns (or features). No rows contain any null values. 
INSERT Image01 HERE  

Step 1: Find the Best Value for k   
To prepare for the first step in this challenge, which was to find the best value for k using a scaled version of the dataframe, I scaled the dataframe using the StandardScaler() module from scikit-learn. From the resulting array, I created a dataframe. To this dataframe of scaled values, I added the index column of the crypto currency names.

In order to find the best value for k, I crated an Elbow Curve. This entailed 
a) creating an empty list to store inertia values
b) creating a for loop to calculate inertia for values of k 1 through 11
c) creating a KMeans model with the loop counter
d) fitting the model to the dataframe of scaled data
e) creating a dictionary, then a dataframe from the model output
f) plotting the Elbow Curve to identify the appropriate value of k, which was 4
INSERt Image 2 HERE

Step 2: Cluster Cryptocurrencies with K-means
To cluster the cryptocurrencies with K-means, using the scaled data, I wrote code to  
a) initialize the K-means model with the best value for k  
b) fit the K-means model using the original scaled DataFrame  
c) predict the clusters to group the cryptocurrencies  

As we can see in the graph below, 4 clusters are plotted, though its difficult to separate cluster 1 from cluster 0. Cluster 3 appears to be an anomoly. Clusters 0 and 2 appear to be reasonably distinct, with minor overlap.  
ISERT IMAGE 03 HERE  

Step 3. Optimize Clusters with Principal Component Analysis  
For this step I used principal component analysis on the scaled data to reduce the features from 7 features down to 3 principal components, PC1, PC2, and PC3.
Using Python to calculate explained variance, I found that 37% of the variance could be explained by PC1, 35% by PC2, and 18% by PC3. The total explained variance was 89.5%.
I then created a new DataFrame with the PCA data and set "coin_id" index from the original DataFrame as the index for the new DataFrame.
I ran a second Elbow Test, using a simmilar process to that described in Step 1, but this time on the PCA data. Again, 4 appeared to be the most appropriate value for k. 
INSERT IMAGE 4 HERE  

Step 4: Cluster Cryptocurrencies with K-means Using the PCA Data
By following a similar process to that described in Step 2, I predicted the clusters to use to group the cryptocurrencies using the PCA data. I then plotted the results. 
The clusters 0 and 2 remained grouped around the x-axis at zero, but appeared more closely clustered withing themselves and with each other. Noticeably, the single 
IMSERT IMAGE 05 HERE


