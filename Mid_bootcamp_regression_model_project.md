# Mid Bootcamp Project – Regression Model

#### Team 3: Tengya Chu, Marc García & Andrea Evrard

### Background and objective

The main objective of the current project is to build a machine learning model to predict the selling prices of houses based on a set of variables on which the value of the house is evaluated. 
Apart from that, we want to understand the relationships between the different variables and the price, as we are particularly interested in knowing which are the factors that are responsible for higher property values (those which are >$650K). 

### Data extraction and column definition

This dataset contains house sale prices for King County, which includes Seattle. It includes homes sold between May 2014 and May 2015.
Particularly, we are presented with the following information: 
-**id**: a notation for a house
-**date**: Date house was sold
-**price**: Price is prediction target
-**bedrooms**: Number of Bedrooms/House
-**bathrooms**: Number of bathrooms/bedrooms
-**sqft_living**: square footage of the home
-**sqft_lot**: square footage of the lot
-**floors**: Total floors (levels) in house
-**waterfront**: House which has a view to a waterfront
-**view**: Has been viewed
-**condition**: How good the condition is Overall
-**grade**: overall grade given to the housing unit, based on King County grading system
-**sqft_above**: square footage of house apart from basement
-**sqft_basement**: square footage of the basement
-**yr_built**: Built Year
-**yr_renovated**: Year when house was renovated
-**zipcode**: zip code
-**lat**: Latitude coordinate
-**long**: Longitude coordinate
-**sqft_living15**: Living room area in 2015(implies-- some renovations) This might or might not have affected the lotsize area
-**sqft_lot15**: lotSize area in 2015(implies-- some renovations)

## Exploring the data 

Since our objective was to build an exploratory or predictive model, we decided to use the **Python** to first analyse all the data. 
To achieve our goal, the first thing we did was to explore and clean the data. The steps we followed were as follow: 
1.	Identify the numerical and categorical values. And convert those columns to its corresponding type (object or float)

2.	Thanks to a heatmap, a correlation matrix, we concluded the variables which were correlated among them. For those columns, we decided to drop some of them as they were not adding any additional value. Besides, we also decided to drop the columns “id” and “date”, since we assumed that they were all personalized numbers for each property and hence, wouldn’t have any impact on the final price. 

3.	We checked if there were any null values but there wasn’t any 

4.	To have a more rigorous dataset, we checked for outliers and dropped those. Here, trying to improve the error coefficient, we also tried to fill them with the median of the corresponding columns, but the opposite effect was created. 

5.	Then, we scaled the numerical values and encoded the categorical values. 

Once we had the first draft of the model build, we visualized the variables using **MySQL**. Thanks to that tool, we identified some irregularities, such as having underrepresented categories, meaning that not many properties fall into those categories. Hence, it gave us the hint of improving the prediction model by dropping the categories that were not meaningful enough. 

## Visualizing the data

The final step was to further explore the relationship between the different factors and the final price using **Power BI**. In this step, we tried to find out the characteristics that explained why some properties were higher valued. With this tool we also had the chance to visualize some relations between the variables and it helped us to have a clearer vision of our model.

## Model

Finally, to build the regression model, we imported different models to compare the accuracies and find the model that best fits our data. 

Firstly, we divided our variables between dependent and independent variables, and then into train and test variables (the ones that the model would train with and the others that would be used to ensure the predictions were accurate). Once we had the variables splitted, we trained and tested the models and then we found out the accuracy of our model. Our best model was the **LightGBM one, which gave us an R-squared of 0.94 in the train variables, and a 0,8926 in the test ones.** 
