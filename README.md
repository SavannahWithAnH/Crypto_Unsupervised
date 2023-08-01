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
- Optimize Clusters with Principal Component Analysis
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
