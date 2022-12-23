# Food Sales Predictions

## Analyzing product and outlet properties for increasing sales

**Andrea Cohen**

### Tasks:
- To help the retailer understand the properties of products and outlets that play crucial roles in increasing sales.
- To help the retailer by using machine learning to make predictions about future sales based on the data provided.

### Data:
Data Source https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

For this data set there were 8523 rows and 12 columns.

### Data Dictionary:
Variable Name	| Description
---| ---
Item_Identifier |	Unique product ID
Item_Weight |	Weight of product
Item_Fat_Content |	Whether the product is low fat or regular
Item_Visibility |	The percentage of total display area of all products in a store allocated to the particular product
Item_Type |	The category to which the product belongs
Item_MRP |	Maximum Retail Price (list price) of the product
Outlet_Identifier |	Unique store ID
Outlet_Establishment_Year |	The year in which store was established
Outlet_Size |	The size of the store in terms of ground area covered
Outlet_Location_Type |	The type of area in which the store is located
Outlet_Type |	Whether the outlet is a grocery store or some sort of supermarket
Item_Outlet_Sales |	Sales of the product in the particular store. This is the target variable to be predicted.

### Methods:

The data was first prepared by cleaning it.
- For exploratory and explanatory analysis: 
  - missing data was imputed 
    - mean imputation for numerical data because the average value would likely be closest to the correct value that is missing 
    - constant imputation for categorical data because there might be a pattern to the missing categorical data).  
  - inconsistencies in categorical data were fixed
- For machine learning with linear regression: 
  - inconsistencies in categorical data were fixed
  - ordinal categorical data was encoded
  - mean imputation was used for float columns
  - constant imputation was used for categorical columns
  - numeric data was scaled
  - object columns were one-hot encoded
- For machine learning with a regression tree model:
  - inconsistencies in categorical data were fixed
  - ordinal categorical data was encoded
  - mean imputation was used for float columns
  - constant imputation was used for categorical columns
  - object columns were one-hot encoded

### Exploratory Data Analysis:

Histograms were used to view the distributions of various features and the target.

#### Distribution of Item Visibility

![Item Visibility.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Item%20Visibility.png)

The most frequent observations are at lower values--most of the items in the stores have a low visibility score.

#### Distribution of Item Outlet Sales

![Item Outlet Sales.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Item%20Outlet%20Sales.png)

There are more frequent observations at lower values--most of the stores have low sales.

### Explanatory Visuals:

Scatterplots were used to compare the item properties to the overall sales.
Barplots were used to find the effect of outlet properties on overall sales.

#### Do higher prices increase the overall sales at the outlet?

![Maximum Item Price vs. Sales.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Maximum%20Item%20Price%20vs.%20Sales.png)

- This scatterplot shows a positive correlation between the maximum price of an item and the overall outlet sales. Outlets with higher maximum prices tend to have higher overall sales. However, we can't assume that higher prices cause higher sales, just because they are correlated.

#### Does the outlet size, the outlet location, or the the outlet type affect the sales?

![The Effect of Outlet Properties on Sales.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/The%20Effect%20of%20Outlet%20Properties%20on%20Sales.png)

- The outlet properties make a difference in overall sales. First, medium-sized stores have the highest sales, and small-sized stores have the lowest sales. Second, tier 2 and 3 locations also have the highest sales. Finally, supermarkets have higher sales than grocery stores. This might indicate that medium and large stores, tier 2 and 3 stores, and supermarkets use more effective sales strategies.

### Machine Learning:

#### Models Evaluated and Results:

- Linear Regression Model:
fitting a line in order to predict the sales
  - Test Scores
    - MAE: 3,178,221,135,989.0835 
    - MSE: 1,968,512,240,476,133,134,342,029,312.0000 
    - RMSE: 44,367,919,046,041.9609 
    - R2: -713493456135360479232.0000
  - the linear regression model explained <0% of the variation.
  - while the model is making an average error of >3 trillion, it is making some much larger errors.

- Regression Tree Model with the max_depth tuned to 5
using decision trees to predict the sales
  - Test Scores
    - MAE: 736.8796 
    - MSE: 1,114,471.1153 
    - RMSE: 1,055.6851 
    - R2: 0.5961
  - the regression tree model explained 60% of the variation.
  - while the model is making an average error of 859.91, it is still making some larger errors

The Regression Tree Model had the lowest MAE and RMSE for the testing data. The Regression Tree Model also had the highest R2 score.
**The Regression Tree Model was the best model, based on the regression metrics for the testing data.**
Using the Regression Tree Model to predict future sales would not be very reliable--the predictions might be off by about 34%, with some larger errors.  However, the model would account for about 60% of the variation in sales.

### Recommendations:

#### Understanding the properties of products and outlets that play crucial roles in increasing sales:
The retailer should increase use of the effective sales strategies (including item visibility and maximum item price) used by medium and large stores, tier 2 and 3 stores, and supermarkets. The retailer should also recognize the room for further growth in small stores, tier 1 locations, and grocery stores--they might need to use different sales strategies in these outlets than in medium and large stores/tier 2 and 3 stores/supermarkets.

#### Predicting future sales based on the data provided:
Overall, the Regression Tree Model was the best model, compared to the Linear Regression Model.  Sales predictions might be off by about 34%, but the model would account for about 60% of the variation in future sales.

### Limitations & Next Steps
The information collected provided some insight into the the properties of the products and outlets, but did not predict future sales well.  The retailer should investigate the effective sales strategies at their highest-selling outlets for an immediate action plan to increase sales.  They should also collect different data--there are clearly other properties about the products and outlets that were not captured in this data set that can predict future sales better.

### For further information

For any additional questions, please contact *andrearcohen7@gmail.com*.
