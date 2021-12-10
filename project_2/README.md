
# GA Project 2 - How to use machine learning to predict Ames price of a house in Ames based on Ames historical housing data

### Background
Properties are illiquid asset, they are not traded as frequently as stocks or treasury bonds, hence the market value of properties are less readily available as stock price or treasury bonds price. Besides, properties are heterogeneous, which means every property is unique in term of its location, the building, floor, direction facing and so on (unlike stocks, your Apple share is the same as my Apple share). This makes pricing for properties difficult and also creates information asymmetry that put buyer or seller at a disadvantage.

What if you can use machine learning to predict the sale price of any property based on their respective attributes?

### Problem Statement
This model will predict the price of a house at sale at Ames, Iowa by creating a linear regression model based on the Ames Housing Dataset. This will benefit potential buyers or sellers who are interested in the housing price of Ames because such data maybe not be as readily available as stock price due to its illiquidity (properties are infrequently traded). The model will be evaluated in term of R2 score in test dataset. A submission will be made to the Kaggle based on test.csv which will be evaluated in term of root mean squared error (RMSE).

### Data Dictionary

Please refer to Data Dictionary below - http://jse.amstat.org/v19n3/decock/DataDocumentation.txt



### EDA and cleaning data

**train.csv**: This dataframe contains 2051 rows (i.e. houses) and 81 columns (i.e. features on the house)

**test.csv**: This dataframe contains 878 rows (i.e. houses) and 80 columns (i.e. features on the house, but exclude sale price)

1. Identify missing values in each column and if there is any columns whose data type is incorrect (eg. numerical columns but read as string)
2. Identify outliers by using boxplot
3. Explore correlation of variables with one another
4. Drop columns that are totally unrelated to the sale price (eg. ID, Parcel ID)
5. Impute null values with mean for numerical features
6. Impute standard string (eg."Not applicable") for categorical features because null value represents that the feature does not exist. Otherwise, impute with mode.

### Preprocessing and Modeling

1. Perform one-hot encoding for categorical columns
2. Split train and test dataset
3. Perform linear regression model as base line model and evaluate its R2 score
4. Perform lasso and ridge model to improve the base line model and evaluate their R2 scores


### Findings

The following features are the top 5 strongest predictive power features in determining sale price (higher the features, higher the sale price):
1. Second floor square feet
2. First Floor square feet
3. Type 1 Basement square feet
4. Total square feet of basement area
5. Rating of the overall material and finish of the house

Property price is highly dependent on its size, be it basement size, first floor size or second floor size.

### Conclusion and Recommendation

1. Larger the size, higher the price.

2. The overall material quality and condition of the house play a big part in improving sale price.

3. Last but not least, houses located in Somerset are highly valued than other neighbourhood.

However, what is highly regarded in US may be less valued in Singapore, and vice versa. For example, we don’t even need a fireplace in Singapore! We need aircon!  

It is then prudent to note that our model is unlikely to be extendable to Singapore’s context.


### References

Kaggle challenge - https://www.kaggle.com/c/dsi-us-11-project-2-regression-challenge/submit
Data Dictionary - http://jse.amstat.org/v19n3/decock/DataDocumentation.txt
