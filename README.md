# House-cost-price-prediction
The project will predict the cost price of houses with the help of linear regrerssion

## Essential Packages required to be installed:

1. Numpy
2. Pandas
3. matplotlib
4. seaborn
5. scipy

## Description:

1. Ensure that the files containing datasets ie. train.csv and test.csv must be imported. The model will be trained on the basis of the results of train.csv file and then model will predict the results for test.csv.

2. We have plotted a distplot for all the values/results of SalePrice in train.csv. Since the skewness and kurtosis for the distplot came out to be quite large thus not acceptable(skewness = 1.8828757597682129, kurtosis= 6.536281860064529), thus we had performed log transformation for the function that made our graph linear with even very less skewness and kurtosis.(skewness= 0.12134661989685333, kurtosis= 0.809519155707878.

3. Skewness determines the normal distribution of the graph in form of floating point numbers. when skewness==0, this shows that dataset is normally distributed.

4. Kurtosis determines the weightage of dataset on the basis of weights of tails. More is the kurtosis, heavier is the tail of dataset.

5. We have then calculated pairwise correlation of each column with every other column using corr() function. This was required to make a heatmap for the dataset that shows correlation of columns graphically.

6. We have thus choosen 10 columns with maximum correlational value with saleprice. Those columns are saved in list of indices: cols.
Those correlation are placed in form of a matrix with the help of numpy.corrcoef() function.

7. We had made scatter plotes between SalePrice with 
  a] TotalBsmtSF
  b] LotArea
  c] GrLivingArea
  d] GarrageArea

8. Afterwards we had done relational exploration of catagorical features using box plotting

9. Make sure to fill all Nan (missing) values in the train as well as test dataframe . We had already combined both of them into a new dataframe called as all_data.
We had also used LabelEncoder that assign label numeral to each and every data value in  a dataseries.

10. Box cox tranformation was required to reduce skewness of some highly skewed data. It is a way to transform non normal depandant variables into a normal shape. This transform was successful with the help of function boxcox1p() present in scipy.special .  We had added some dummy catagorical features using pandas.get_dummies().

11. For linear regression modelling, I've made use of Lasso Regression and Gradient Boost Regression methods.
  a] Lasso Regression: a type of linear regression that uses shrinkage. Data values are shrinked towards a central point like mean.
  b] Gradient Boosting Regression: used for identifying errors in prediction. It minimizes overall error by combining existing and prevois model.

12. Other important things used here include usage of RobustScaler, k-fold cross validation and transformer Mixin
  a] RobustScaler: This scaler removes median and scales data according to quantile range
  b] k- fold cross validation: provides train/test indices to split data in train/test sets
  c] Transformer Mixin: Mixin class for all tranformers

13. We made a class AveragingModels that finds the average between the predictions of Lasso and Gradient boosting regression. 

14. Finally we made accurate predictons from our side and stored them all in submission.csv file.

this project was made with the reference to the machine learning project of itsmuriuki, you can find same project on the link below
https://github.com/itsmuriuki/Predicting-House-prices
This project was made for learning perspective.
The data set for the model can also be found at kaggle, below is the link to access dataset.
https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data
