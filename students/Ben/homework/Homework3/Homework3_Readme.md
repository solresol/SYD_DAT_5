
## Homework - Due July 25th 2016

* For the following, continue to use the github repository you made for your project
* You don't have to use the same data that you used from the previous homework assignment if you have decided to change what your project is about.

### Identify some attributes where you would expect clustering to be successful.

- Robot Strength and Supplier Cost 
- Cost Per Strength and robot strength 
- Cost Per Strength and Supplier Cost

### Try two or more different clustering algorithms, and experiment with different numbers of clusters.
- k-means 
- denisty scan 

### If the clustering works well, try to give descriptive names for the different clusters you have found. If the clustering isn't successful, try to hypothesise why your data is some homogenous (and try clustering on different attributes).

K-Means Clustering works well. 

Kmeans cluster graphs are below: 

* Clusters of Supplier Cost based on robot strength

![tag](cluster_Strength&Cost.png)

The silhouette score is 0.581. 

* Clusters of Robot Strength based on cost per strength

![tag](cluster_CPS_and_robot_strength.png)

The silhouette score is 0.5675

* Clusters of Supplier Cost based on Cost Per Strength 

![tag](cluster_SupplierCost_and_costPerStrength.png)

The silhouette score is 0.5776

Dbscan cluster couldn't be performed as the dbscan code couldn't produce clusters. The input and output are as below:

dbscan = sklearn.cluster.DBSCAN(eps=0.3, min_samples=3)
dbscan_cs= dbscan.fit(target_info)
dbscan_cs.labels_ 
Output: 

array([-1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1, -1,
       -1], dtype=int64)


### Try building decision trees on your data. If you think simplicity would be good, try to make it as simple as possible. If you think accuracy is more important, use ensembling or any other techniques that you have learned.

* Bagging Regressor with scatter plot of predicted y values and actual y values as below:
 
![whatever](baggingRegScat.png)

* Random Forest Tree with scatter plot of predicted y values and actual y values as below:

![whatever](RandomFroestTreeScat.png)

### Modify one of the models you have created so that you can evaluate its bias-variance trade-off. 

The selected model is Lasso model with Robot Strength data as X and Supplier Cost as y. A train_test_split with test size of 0.3 was performed. The model provided the following statistical values: 
* explained_variance_score = 0.846
* mean_absolute_error = 39552
* median_absolute_error = 32887
* Coefficient of determination (r2) = 0.840

The definition of As explained variance ratio is the ratio of the explained variance( variance of the model's predictions)  to the total variance. (sample variance of the dependent variable)
The definition of R2 is that the proportion of the variance in the dependent variable that is predictable from the independent variable. 

Both explained variance ratio and R2 is the numerical indication that the created Lasso regression line fits 84% well with the real data point. The interpretation is 84% of the varibility in the selected actual values of supplier cost can be explained by the predicted values of supplier cost. 

The mean absolute error and median absolute error are quantities used to measure how close forcasts or predictions are to the eventual outcomes. 

The mean absolute error is the average of the absolute errors between the predicted supplier cost and the actual supplier. The mean value of all supplier cost is 251976. The ratio of mean_absolute_error and mean of total is 15.6% and ratio of median_absolute_error and mean of total is 13.05% 


#### K-Fold Cross Valuation 

10 folds of cross validation were applied with the following mean values: 
* r2 = -1.025? 
* mean_abolute_error = 54163
* median_abolute_error = 49002
As the computed r2 value is negative, it indicates something has gone wrong...

#### GridSearch 

GridSearch with 6 folds and paramatters of 'fit_intercept', 'normalize', 'copy_X and 'alpha' was applied. The resulted GridSearch best scores are as below: 

* r2= 0.79
* mean_abolute_error = 44794
* median_abolute_error = 37281

Comparing the results from GridSearch with a simple train_test_split evaluation, it's seen that the model performance has decreased with GridSearch. In other words,  there was positive bias with the train_test_split evaluation and the computed model performance  was exceptionally high. GridSearch brought the performance lower with reduced positive bias. 

