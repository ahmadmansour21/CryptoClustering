# CryptoClustering
The code for the following challenge can be found within the file "Crypto_Clustering.ipynb", which can be found within the CryptoClustering repository.

All of the code was written completely independently and with the help of the Xpert AI tool.

1) Prepare the data
StndardScaler() was used and applied to all columns with numerical values in the dataframe in order to normalize this data. Once successful, a new dataframe is created with all of the original columns and rows but now with the scaled data, which will be the dataframe used for subsequent coding.

2) Find the best value for k
First, a list with k-values ranging from 1-11 was created and the associated inertia values for each k were found using a for loop. This was then converted to a dataframe in order to generate the plot. Finally, the elbow curve was generated using hvplot.line. Using the elbow method to analyze the graph and the table, the best value for k was determined to be k =3 (see code sheet for explanation).

3) Cluster cryptocurrencies with k-means
Now that the best value for k is identified, it is used for further analysis. In this portion, we wish to uncover and plot the kMeans values for each cryptocurrency in the original dataframe. This best value for k was inserted in a kMeans model and this model was made to fit the scaled dataframe. Next, kmeans_model.predict() was used to predict the clusters and group the Cryptocurrencies accordingly. The data on the clusters was added as a column to the scaled dataframe and this data was plotted using hvplot yet again.

4) Optimize Clusters with Principal Component Analysis
Here, a PCA model was used to optimize the previously found clusters. Thus, PCA(n_components=3) was employed and the number 3 was chosen based on part 2. Next, the scaled dataframe from above was reduced to 3 components, as is usually the case with PCA using pca.fit_transform() and then this was turned into a dataframe. Then, using pca.explained_variance_ratio_ we were able to get the variance for each component which resulted in a combined variance of 0.895. Finally, a proper dataframe is formed with all of the rows of the original dataframe containing the cyptocurrencies and the PCA components.

5) Find the Best Value for k Using the Scaled PCA DataFrame
Same code as part 2 but using the pca dataframe this time.

6) Cluster Cryptocurrencies with K-means Using the Scaled PCA DataFrame
Again, same code as part 3 but using the pca dataframe.

7) Visualize and Compare the Results
This section used "*" to combine the plots and create composite plots for comparing.
