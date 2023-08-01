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
~~~
# Plot a line chart with all the inertia values computed with 
# the different values of k to visually identify the optimal value for k.
pca_plot = elbow_pca_df.hvplot.line(
    x='k',
    y='inertia',
    title='PCA Curve'
)

pca_plot
~~~

- Cluster Cryptocurrencies with K-means Using the PCA Data
~~~
# Create a scatter plot using hvPlot by setting 
# `x="PC1"` and `y="PC2"`. 
# Color the graph points with the labels found using K-Means and 
# add the crypto name in the `hover_cols` parameter to identify 
# the cryptocurrency represented by each data point.
pca_scatter =crypto_predict_pca_df.hvplot.scatter(
    x='PC1',
    y='PC2',
    by='like_segments',
    hover_cols=['coin_id'],
    marker=['star', 'square', 'hex', 'triangle'],
    title='PCA Crypto Clusters'
)
pca_scatter
~~~


### Elbow Curve Comparison
<img width="1034" alt="image" src="https://github.com/SavannahWithAnH/Crypto_Unsupervised/assets/126124356/df187cfd-641f-4298-9a29-5b7ba78bbfd7">

### Cluster Comparison

<img width="1034" alt="image" src="https://github.com/SavannahWithAnH/Crypto_Unsupervised/assets/126124356/aefa68c2-1a12-4050-99ee-3fadcff4450c">



I attended office hours where an instructor assisted with this project.


<br>
<br>  
<br>  

### Questions?
Please refer to the following:  
[My LinkedIn Page](https://www.linkedin.com/in/savannah-porter-7a2627267/)  
[My Email Contact](savannahnporter@gmail.com)  
<br>
[buy this analyst some much needed coffee](www.venmo.com/SavannahP519)
