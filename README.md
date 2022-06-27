# Cryptocurrencies

The purpose of this project was to leverage unsupervised machine learning in order to cluster cryptocurrency data and to create a classification system based on various attributes of the currencies (including the total amoumt mined, total supply of the currency, its algorithm, etc.). Martha is a senior manager for the Advisory Services Team at Accountability Accounting, one of your most important clients. Accountability Accounting, a prominent investment bank, is interested in offering a new cryptocurrency investment portfolio for its customers. The company, however, is lost in the vast universe of cryptocurrencies. So, they’ve asked you to create a report that includes what cryptocurrencies are on the trading market and how they could be grouped to create a classification system for this new investment.

The data Martha will be working with is not ideal, so it will need to be processed to fit the machine learning models. Since there is no known output for what Martha is looking for, she has decided to use unsupervised learning. To group the cryptocurrencies, Martha decided on a clustering algorithm. She’ll use data visualizations to share her findings with the board.


This was accomplished in four steps:

- The data had to be pre-processed and transformed in order to facilitate the use of the algorithm;
- Principal Component Analysis (PCA) was applied to reduce the dataset into three components;
- The data was fed through the K_Means algorithm in order to cluster the data into specific groups, and the results were visualized in a 3D scatterplot;
- Additional visualizations (i.e. table and 2D scatterplot) created to aid in the analysis.

## Deliverables:
This new assignment consists of three technical analysis deliverables and a written report.

1. ***Deliverable 1:*** Preprocessing the Data for PCA
2. ***Deliverable 2:*** Reducing Data Dimensions Using PCA
3. ***Deliverable 3:*** Clustering Cryptocurrencies Using K-means
4. ***Deliverable 4:*** Visualizing Cryptocurrencies Results


## Deliverables:
This new assignment consists of three technical analysis deliverables and a proposal for further statistical study:

* Data Source: `crypto_data.csv`
* Data Tools:  `crypto_clustering_starter_code.ipynb`.
* Software: `Python 3.9`, `Visual Studio Code 1.50.0`, `Anaconda 4.8.5`, `Jupyter Notebook 6.1.4` and `Pandas`

### DELIVERABLE RESULTS:
## Deliverable 1

1. Remove cryptocurrencies not being traded.
2. Keep all the cryptocurrencies that have a working algorithm
3. The `IsTrading` column it was dropped.
4. Rows that have null value were dropped.
5. Filter dataset with only mined coins.
6. Create a new DataFrame `CoinNames`, and use the index from the previous dataset as the index for this new DataFrame `cc_names_df`  
7. 7. Remove `CoinName` unnecessary column from the DataFrame `crypto_df`    

![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s1.png)


![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s2.png)


![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s3.png)


# Deliverable 2:  
## Reducing Data Dimensions Using PCA 
Using your knowledge of how to apply the Principal Component Analysis (PCA) algorithm, you’ll reduce the dimensions of the `X` DataFrame to three principal components and place these dimensions in a new DataFrame.

The analysis from DataFrame, `pcs_df` includes columns `PC 1`, `PC 2`, and `PC 3`, and uses the index of the `crypto_df` DataFrame as the index.  

![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s4.png)

# Deliverable 3:  
## Clustering Cryptocurrencies Using K-means 

Run analysis of clusters for the dataset `pcs_df`, including plotting an elbow curve with `hvplot` to find the value for `K`.  
![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s5.png)


By running an analysis using K=4 and applying the K-means algorithm, got the below results:
![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s6.png)


Build a new dataframe names: `clustered_df` 

* Adding the `CoinNames` column from the `cc_names_df` dataset created.  
* Merging the `crypto_df` and `pcs_df` DataFrames with the same index.
![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s7.png)


## Deliverable 4
### Visualizing Cryptocurrencies Results

A new dataset is created using the `MinMaxScaler().fit`_transform method to scale the `TotalCoinSupply` and `TotalCoinsMined` columns from the `clustered_df`, adding the `CoinName` from `cc_names_df` and the `Class` column from `clustered_df`.

A 2D hvplot scatter plot with `x="TotalCoinsMined_scaled"`, `y="TotalCoinSupply_scaled"`, and `by="Class"` with the `CoinName` displayed.

Class 2 and Class 3 are the same; Classes 0 and 1 gave out three different Classes: 0, 1, 4.

![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s10.png)


![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s11.png)


![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s12.png)


![d1](https://github.com/SLCunningham21/Cryptocurrencies/blob/main/Resources/Images/s13.png)





