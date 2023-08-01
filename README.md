# Crypto_Unsupervised
### (Analyzing cryptocurrencies using unsupervised machine learning-Python)

The following steps were taken to produce this deliverable.

- Prepare the Data
~~~
  # Use the `StandardScaler()` module from scikit-learn to normalize the data from the CSV file
  stscaled_data = StandardScaler().fit_transform(market_data_df)
  stscaled_data
~~~
     
- Find the Best Value for k Using the Original Scaled DataFrame
~~~
# Plot a line chart with all the inertia values computed with 
# the different values of k to visually identify the optimal value for k.
elbow_plot = elbow_data_df.hvplot.line(
    x='k',
    y='inertia',
    title="Crypto Elbow",
    xticks=k
)
elbow_plot
~~~

- Cluster Cryptocurrencies with K-means Using the Original Scaled Data
~~~
# Initialize the K-Means model using the best value for k
model = KMeans(n_clusters =4)

# Fit the K-Means model using the scaled data
model.fit(stscaled_data_df)

# Predict the clusters to group the cryptocurrencies using the scaled data
crypto_clusters = model.predict(stscaled_data_df)

# Print the resulting array of cluster values.
crypto_clusters
~~~

- Optimize Clusters with Principal Component Analysis
~~~
# Use the PCA model with `fit_transform` to reduce to 
# three principal components.
crypto_pca = pca.fit_transform(predict_df)

# View the first few rows of the DataFrame. 
crypto_pca[:6]
~~~

- Find the Best Value for k Using the PCA Data
- Cluster Cryptocurrencies with K-means Using the PCA Data





buy me coffee link.


I attended office hours where an instructor assisted with this project.


<br>
<br>  
<br>  

### Questions?
Please refer to the following:  
[My LinkedIn Page](https://www.linkedin.com/in/savannah-porter-7a2627267/)  
[My Email Contact](savannahnporter@gmail.com) 
