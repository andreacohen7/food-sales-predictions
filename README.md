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

### Exploratory Data Analysis

Histograms were used to view the distributions of various features and the target (sales).

#### Distribution of Item Visibility

![Item Visibility.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Item%20Visibility.png)

The most frequent observations are at lower values--most of the items in the stores have a low visibility score.

#### Distribution of Item Outlet Sales

![Item Outlet Sales.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Item%20Outlet%20Sales.png)

There are more frequent observations at lower values--most of the stores have low sales.

### Explanatory Visuals

Scatterplots were used to compare the item properties to the overall sales.
Barplots were used to find the effect of outlet properties on overall sales.

![Maximum Item Price vs. Sales.png](https://github.com/andreacohen7/food-sales-predictions/blob/main/Maximum%20Item%20Price%20vs.%20Sales.png)



### Model

Describe your final model

Report the most important metrics

Refer to the metrics to describe how well the model would solve the business problem

## Recommendations:

More of your own text here


## Limitations & Next Steps

More of your own text here


### For further information


For any additional questions, please contact **email**
