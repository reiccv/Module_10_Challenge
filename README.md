# Module 10 Challenge


## Challenge: Crypto Clustering

The steps for this challenge are broken out into the following sections:

- [Import the Data](###import the data)
- [Prepare the Data](###prepare the data)
- [Find the Best Value for k Using the Original Data](###Find the Best Value for k Using the Original Data)
- [Cluster Cryptocurrencies with K-means Using the Original Data](###Cluster Cryptocurrencies with K-means Using the Original Data)
- [Visualize and Compare the Results](###Visualize and Compare the Results)

### Import the Data

This section imports the data into a new DataFrame. It follows these steps:

1. Read  the “crypto_market_data.csv” file from the Resources folder into a DataFrame, and use `index_col="coin_id"` to set the cryptocurrency name as the index. Review the DataFrame.

2. Generate the summary statistics, and use HvPlot to visualize your data to observe what your DataFrame contains.

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/import1.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/import2.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/import3.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/import4.PNG)


### Prepare the Data

This section prepares the data before running the K-Means algorithm. It follows these steps:

1. Use the `StandardScaler` module from scikit-learn to normalize the CSV file data. This will require you to utilize the `fit_transform` function.

2. Create a DataFrame that contains the scaled data. Be sure to set the `coin_id` index from the original DataFrame as the index for the new DataFrame. Review the resulting DataFrame.

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/prepare1.PNG)


### Find the Best Value for k Using the Original Data

In this section, i will use the elbow method to find the best value for `k`.

1. Code the elbow method algorithm to find the best value for `k`. Use a range from 1 to 11. 

2. Plot a line chart with all the inertia values computed with the different values of `k` to visually identify the optimal value for `k`.

Repeat for PCA

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/bestkavlue1.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/bestk2.PNG)


### Cluster Cryptocurrencies with K-means Using the Original Data

In this section, I will use the K-Means algorithm with the best value for `k` found in the previous section to cluster the cryptocurrencies according to the price changes of cryptocurrencies provided.

1. Initialize the K-Means model with four clusters using the best value for `k`. 

2. Fit the K-Means model using the original data.

3. Predict the clusters to group the cryptocurrencies using the original data. View the resulting array of cluster values.

4. Create a copy of the original data and add a new column with the predicted clusters.

5. Create a scatter plot using hvPlot by setting `x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`. Color the graph points with the labels found using K-Means and add the crypto name in the `hover_cols` parameter to identify the cryptocurrency represented by each data point.

Repeat for PCA


![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/cryptoclusters1.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/clsuters2.PNG)

### Visualize and Compare the Results

In this section, you will visually analyze the cluster analysis results by contrasting the outcome with and without using the optimization techniques.

1. Create a composite plot using hvPlot and the plus (`+`) operator to contrast the Elbow Curve that you created to find the best value for `k` with the original and the PCA data.

2. Create a composite plot using hvPlot and the plus (`+`) operator to contrast the cryptocurrencies clusters using the original and the PCA data.


![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/comparecurves.PNG)

![text](https://github.com/reiccv/Module_10_Challenge/blob/main/Resources/sgementclusters.PNG)