## Predicts whether a person makes more than $50,000 or not using XGBoost.

What we did here -
* Import all the required libraries/modules.
* Load the data from the 'adult.data' file using pandas. Its a categorical dataset.
* Use False for the header parameter while reading data. As the data has not column names, so we mention column names manually.
* The Dataset has 32561 rows and 15 columns.
* There are no null values but 0s are present in huge quantity. Also, dataset has '?' in some columns. We have to handle both.
* On the basis of uniqueness of values in columns, we dropped 7 columns. And two columns are dropped which were containing most of the 0s.
* Three columns were conatining '?'. so we converted those values into null and dropped those rows.
* So, after all this we have dataset of 30718 rows and 8 columns.
* Now we head to convert the categorical data into int type.
* We have our target column named as 'Wage'. 1 represents the wage is above $50k and 0 states the wage is equal to $50k or less.
* Plotted bar graphs to check the data distribution.

![img1](/img/xg1.PNG)

* Check for the outliers as well.

![img2](/img/xg2.PNG)

* Standardized the feature columns and checked the VIF values. Vif values are in range of 1.005-1.169., which is good to go.
* Further, split the data for training and testing process.
* Use XGBClassifier with n_estimator=70 and max_depth=4 (can use other values for better accuracy score).
* Also, use eval_metric='logloss' (Log loss penalizes false classifications by taking into account the probability of classification).
* Model score on testing data is 82%. We got same accuracy on predicted data.
* The confusion matrix -

![img3](/img/xg3.PNG)

* AUC score is 73%
* Last, the ROC curve -

![img4](/img/xg4.PNG)
