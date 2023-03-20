# AutoML Marketting Campaign

In this assignment, you will an AutoML library like H2O.ai to create predictive models and interpret them. Find a significant relation for each algorithm of your choosing in your data. Create multivariate models.

For the moment you will assume the data is good. In future assignments, you will check your data, fix data issues and do some feature engineering. 

## About Dataset - Marketing Campaign

Dataset Link - https://www.kaggle.com/datasets/rodsaldanha/arketing-campaign

**Context**
A response model can provide a significant boost to the efficiency of a marketing campaign by increasing responses or reducing expenses. The objective is to predict who will respond to an offer for a product or service

**Content**

1. AcceptedCmp1 - 1 if customer accepted the offer in the 1st campaign, 0 otherwise
2. AcceptedCmp2 - 1 if customer accepted the offer in the 2nd campaign, 0 otherwise
3. AcceptedCmp3 - 1 if customer accepted the offer in the 3rd campaign, 0 otherwise
4. AcceptedCmp4 - 1 if customer accepted the offer in the 4th campaign, 0 otherwise
5. AcceptedCmp5 - 1 if customer accepted the offer in the 5th campaign, 0 otherwise
6. Response (target) - 1 if customer accepted the offer in the last campaign, 0 otherwise
7. Complain - 1 if customer complained in the last 2 years
8. DtCustomer - date of customer’s enrolment with the company
9. Education - customer’s level of education
10. Marital - customer’s marital status
11. Kidhome - number of small children in customer’s household
12. Teenhome - number of teenagers in customer’s household
13. Income - customer’s yearly household income
14. MntFishProducts - amount spent on fish products in the last 2 years
15. MntMeatProducts - amount spent on meat products in the last 2 years
16. MntFruits - amount spent on fruits products in the last 2 years
17. MntSweetProducts - amount spent on sweet products in the last 2 years
18. MntWines - amount spent on wine products in the last 2 years
19. MntGoldProds - amount spent on gold products in the last 2 years
20. NumDealsPurchases - number of purchases made with discount
21. NumCatalogPurchases - number of purchases made using catalogue
22. NumStorePurchases - number of purchases made directly in stores
23. NumWebPurchases - number of purchases made through company’s web site
24. NumWebVisitsMonth - number of visits to company’s web site in the last month
25. Recency - number of days since the last purchase

Answer the following questions for all of the models:

* Is the relationship significant?

* Are any model assumptions violated?

* Is there any multicollinearity in the model?

* In the multivariate models are predictor variables independent of all the other predictor variables?

* In in multivariate models rank the most significant predictor variables and exclude insignificant ones from the model.

* Does the model make sense?

* Does regularization help?

* Which independent variables are significant?

* Which hyperparameters are important?

* Coding professionalism?

## Abstract

Market Sales data contains customer specific information about a customers details like age, income and shopping habits like amount spent, website visits etc. We aim to find if a customer will repond positively to a marketting campaign or not. Using AutoML we aim to find the best classification model. Use Regularization to check if model improved or not and try tuning hyperparameters for best results. We also check the relationships we get between multivariate models and if the models make sense.

Answer the following questions for all of the models:

* **Is the relationship significant?**
  
  From the OLS method it was observed that p value for almost all variables was 0 except age, income and complain which suggests that all other relationships are very significant

* **Are any model assumptions violated?**

 no, the model is a multiclassification which did not violate any assumptions

* **Is there any multicollinearity in the model?**

 Multicollinearity can be determined by calculating VIF or correlation matrix, from our correlation matrix we can see that dummy variables for maritial status have high collinearity of -1 and +1 as it is expected for dummy variables. But we also have high collinearity between AmountPurchases, NumPurchased and Income

* **In the multivariate models are predictor variables independent of all the other predictor variables?**
 
 As stated before from correlation matrix not all variables are independent, Income, NumPurchased and AmtPurchased are somewhat dependant to a certain degree to each other

* **In in multivariate models rank the most significant predictor variables and exclude insignificant ones from the model.**
  
  The variable importance ranked -
  1.   Prev_campaign
  2.   Dt_Customer
  3.   Recency
  4.   Amount Spent


* **Does the model make sense?**
  Yes, The model has low logloss, the confusion matrix shows few errors and accuracy close to 90%. Further the model can be improved by hyperparameter tuning
* **Does regularization help?**
  No, as stated above from the regularization results it did not help for this particular dataset
* Which independent variables are significant?
  Significant. independant variables -
  1.   Prev_campaign
  2.   Dt_Customer
  3.   Recency
  4.   Amount Spent
  5.   Income
  6.   Num web visits

* **Which hyperparameters are important?**
  
  The best hyperparameters for this model are:- col_sample_rate of 1.0, learn_rate of 0.10, max_depth of 5, and sample_rate of 0.9


## Conclusion

A basic algorithm based on the logistic regression technique to forecast consumer response to marketing campaigns was created. Some of the independent variables were thought to be ignored by correlation, p-values, and other tests. The variables from the dataset of the Marketing Campaign were trained and tested using the H20.ai framework. This produced the best model, "Stacked Emsemble," which included different GBM and XGBOOST models and had an accuracy of 89.9% for test data. The results indicate that the suggested model can assess and forecast if the client would respond positively to a certain level. The model has to be improved in future studies as the prediction accuracy is admittedly still constrained in several areas. In further investigation of the associated models, several methodologies, such as removing outliers and normalization or booster can help achieve better prediction.
