###CryptoClustering

Using Python and unsupervised learning to predict if Cryptocurriencies are affected by 24 hour or 7 day price changes 

## Prepare the Data
Using the StandardScaler() module from scikit-learn to normalize the data from the CSV file. Create a DataFrame with scaled data and set the "coin_id" index from the original as the index for the new DataFrame.

## Find the Best Value for k Using the Original Scaled DataFrame
Use the elbow method to find the best values for k and create a loop to compute inertia, then plot a line chart with inertia values of k to visually identify the optimal value of k.

## Cluster Cryptocurrencies with K-means Using the Original Scaled Data
Initialize the K-means model with the best value for k. Fit the K-means model using the original scaled DataFrame. Predict the clusters to group the cryptocurrencies using the original scaled DataFrame. Create a copy of the original data and add a new column with the predicted clusters. Create a scatter plot using hvPlot as follows: with the x-axis as "PC1" and the y-axis as "PC2". Color the graph points with the labels found using K-means. Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.

## Optimize Clusters with Principal Component Analysis
Using the original scaled DataFrame, perform PCA and reduce the features to three principal components. Retrieve the explained variance to determine how much information can be attributed to each principal component. What is the total explained variance of the three principal components? Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

## Find the Best Value for k Using the PCA Data
Use the elbow method on the PCA data to find the best value for k. Create a list of k-values and an empty list to store the inertia values. Create a for loop to compute the inertia with each possible value of k. Create a dictionary with the data to plot the Elbow curve. Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k. What is the best value for k when using the PCA data? Does it differ from the best k value found using the original data?

## Cluster Cryptocurrencies with K-means Using the PCA Data
Initialize the K-means model with the best value for k. Fit the K-means model using the PCA data. Predict the clusters to group the cryptocurrencies using the PCA data. Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters. Create a scatter plot using hvPlot set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d" and color the graph points with the labels found using K-means. Then add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point. What is the impact of using fewer features to cluster the data using K-Means?


# References used 
[scikit-learn PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)

[scikit-learn StandardScaler](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html)

[scikit-learn preprocessing data](https://scikit-learn.org/stable/modules/preprocessing.html#preprocessing-scaler)

[scikit-learn Python library](https://scikit-learn.org)

[hvPlot customization](https://hvplot.holoviz.org/user_guide/Customization.html)

[Composing Plots](https://holoviz.org/tutorial/Composing_Plots.html)
