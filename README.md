# Predicting Product Sales
## Analysis of MRP and related columns to identify methods of boosting sales 

**Author**: Matt S.

### Business problem:
Determine sales for food items based off of the store and see which properties are more applicable for generating more sales.


### Data:
Data source: https://datahack.analyticsvidhya.com/contest/practice-problem-big-mart-sales-iii/

Data dictionary:
| Variable Name	| Description |
|:-------------:|:-----------:|
|Item_Identifier	| Product ID |
|Item_Weight | Weight of product |
|Item_Fat_Content	| Whether the product is low-fat or regular|
|Item_Visibility | The percentage of total display area of all products in a store allocated to the particular product |
|Item_Type | The category to which the product belongs |
|Item_MRP	Maximum | Retail Price (list price) of the product |
|Outlet_Identifier | Store ID |
|Outlet_Establishment_Year | The year in which store was established |
|Outlet_Size | The size of the store in terms of ground area covered |
|Outlet_Location_Type | The type of area in which the store is located |
|Outlet_Type | Whether the outlet is a grocery store or some sort of supermarket |
|Item_Outlet_Sales | Sales of the product in the particular store. This is the target variable to be predicted. |



## Methods
Muliple steps were taken to prepare and review the data including:
- Initial data inspection and cleaning
- Exploratory Data Analysis
- Explanatory Data Analysis
- Data pre-processing for ML after exploratory and explanatory analysis
- Linear regression, decision tree, and random forest modeling

## Results
### Outlet_Sales vs Outlet_Type
![](https://github.com/hokushrine/prediction-of-product-sales/blob/main/images/average_sales_vs_outlet_type.png)
- Supermarket Type 3 generates many more sales than its Type1 and Type2 counterparts. Grocery stores have a very low amount of sales.

### Outlet_Sales vs Item_MRP
![](https://github.com/hokushrine/prediction-of-product-sales/blob/main/images/outlet_sales_vs_item_mrp.png)
-  Surprisingly, the higher the MRP, the higher the amount of sales. It was initially expected that lower MRP items would have more sales due to easier purchasability of consumers.
- Further investigation into the more popular items can be determined by sorting items by their MRP.

## Model
Models used:
```
- Linear Regression
- Decision Tree
- Tuned Decision Tree
- Random Forest
- Tuned Random Forest
```
### Final Model Output
Linear Regression Training Scores:

Results for training data:
  - R^2 = 0.562
  - MAE = 847.126
  - MSE = 1297557.55
  - RMSE = 1139.104

Results for testing data:
  - R^2 = 0.567
  - MAE = 804.119
  - MSE = 1194350.684
  - RMSE = 1092.864

-------
Decision Tree Training Scores:

Results for training data:
  - R^2 = 0.604
  - MAE = 762.61
  - MSE = 1172122.773
  - RMSE = 1082.646

Results for testing data:
  - R^2 = 0.595
  - MAE = 738.317
  - MSE = 1118185.973
  - RMSE = 1057.443

-------
Random Forest Training Scores:

Results for training data:
  - R^2 = 0.938
  - MAE = 296.606
  - MSE = 182863.811
  - RMSE = 427.626

Results for testing data:
  - R^2 = 0.56
  - MAE = 766.068
  - MSE = 1214585.128
  - RMSE = 1102.082


- Linear regression has an overall low R2 of training 56%/testing 57%
- Decision tree has an overall low R2 of 60%/testing 59%
- Random forest has a major overfitting issue as indicated by the high training R2 of 93% but low testing R2 of 56%.
All models need further experimenting with tuning in their current state. The best model at the moment is the decision tree model, as it offers a near 1:1 R2 for both training, albeit at 60%.

The decision tree and random forest are both contenders for best models after further tuning is done.

## Recommendations:
Continue tuning the models, as the current results are not at acceptable levels.


## Limitations & Next Steps
- Refactor code to be more modular (move code into functions etc.)
- Continue tuning decision tree and random forest model
- Refer to "To-Do" section in notebook for in-depth next steps
