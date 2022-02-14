Approach

The problem was formulated as a Simple Regression Model with H20 AutoML. I chose H20 AutoML as it takes away the manual effort involved in Hyperparameter Tuning, and is faster, so that we can spend more time on understanding the Data


Steps Involved :

1) Data Preporocessing : Tried various transformations on Views and Followers, such as Log Transform, Sqrt Transform but there wasn't much improvement in R2 score

Age Binning : Binning was done to group age into equal sized Quantiles. Performed Better than Manual Binning. This is because manual binning introduces skewness in the data, and the feature loses its relative importance

2) Feature Engineering : Created a Feature called Views/Followers which is a simple representation for number of views per followers

3) Outlier Detection and Removal : Used Box Plots to detect and remove Outliers. Data with Engagement Score of < 1.025 were removed

4) Modelling : Ran H2o AutoMl which did a 5 fold CV, and chose a stacked GBM as the final model. The CV scores were consistent


What did not Work
1) User-User Collaborative Filtering gave a Public LB R2 score of less than 0.4 (around 0.38) and was therefore ignored at the expense of Tree Based Regression Algorithm

Future Scope:

ALS ( Alternating Least Squares) Algorithm works on distributed systems. 
ALS is implemented in Apache Spark ML and is usually used to solve large scale collaborative filtering problems 
For reference refer to my past work where I built a Recommendation System using ALS : https://github.com/swapnasamirshukla/ALS-Recommendation
