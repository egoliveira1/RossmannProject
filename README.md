# Sales volume forecast for Rossmann Drugstores

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/banner_rossmann.png)

#### This project was made by Eron Oliveira.

# 1. Business Problem.

**The company:**<br>
Dirk Rossmann GmbH, with 56,300 employees in Europe and 4,244 stores, including 2,233 in Germany, is one of the largest drugstore chains in Europe. In 2020, the ROSSMANN Group achieved average sales of 10.35 billion euros in Germany, Poland, Hungary, Czech Republic, Albania, Kosovo, Spain, and Turkey.
The ROSSMANN range is highly customer-oriented. The product range comprises approximately 21,700 items and varies by store location and size. The average sales area of ​​ROSSMANN drugstores is 590 square meters.
In 2014, a new store image was launched, with warmer colors, new product ranges, an attractive customer orientation system, and lots of indirect light to improve the close relationship with the customer.

**The problem:**<br>
Implementing store improvements requires well-structured financial planning with a small margin of error, preventing the company from wasting money on implementing the initiatives.
The main difficulty encountered by the CFO was to know how much each store sold and how much would sell in the short term.
Furthermore, there was no easy, automated, standardized way to obtain this information.
Asking managers to forecast each store's sales over the next six weeks meant that each manager would use a different way to get the data, using different approaches, metrics, and variables.

# 2. The solution
The solution aims to create an intelligent model that uses sales data from all stores and their main characteristics to forecast sales in a future period. A TelegramBot will be used to streamline and facilitate the delivery of information.

## 2.1 Solution Strategy

My strategy to solve this challenge was:

**Step 01. Data Description:**

**Data overview**

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/rossmann_data_description.png)

**Interesting points:**

- The **mean sales** value is around **5,773.82 EUR**.

- There was a **maximum of 7,388 customers** in a single day.

- There are **competitors only 20 meters** away.

**Step 02. Feature Engineering:**
At this stage, there was the transformation and creation of new features to enable a more complete analysis.

**Step 03. Data Filtering:**
Variable transformations and creations made some Dataset columns useless, so those rows and columns were excluded in this step.

**Step 04. Exploratory Data Analysis:**
Univariate, bivariate and multivariate data analyzes were performed, obtaining statistical properties of each one of them, correlations and testing hypotheses. More details will be exposed in the following steps.

**Step 05. Data Preparation:**
At this point, actions of rescaling and transformation of the variables were carried out, seeking a uniformity of data.

**Step 06. Feature Selection:**
The most statistically relevant features were selected using the Boruta package. Also, variables that proved to be relevant in the EDA but were not classified by Boruta were included.

**Step 07. Machine Learning Modelling:**
Some machine learning models were trained. After cross-validation, the one with the best results went through a new stage of fine-tuning hyperparameters to optimize the generalization of the model.

**Step 08. Convert Model Performance to Business Values:**
This point is especially important. It is a sales forecast that will influence an investment that will be made by the company, so the model error percentages need to be very small.

**Step 09. Deploy Model to Production:**
The model is deployed on a cloud environment to make it possible that other stakeholders and services, like TelegramBot,  access its results.

# 4. Top 3 Data Insights

The hypotheses were developed through the creation of a mind map, where the variables that influence the business model were listed.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/MindMapHypothesis.png)

**Hypothesis 01:**
Shops with greater product assortment should sell more.<br>
**FALSE** - Shops with **GREAT ASSORTMENT** of products sell **LESS**.<br>
Although this hypothesis has low relevance for the model, it indicates something interesting for the business. In Rossmann's business model and considering the available variables, it is not necessary to have a wide variety of products to sell more.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/hyp_1_assortment.png)

**Hypothesis 02:**
Shops with closer competitors should sell less.<br>
**FALSE** - Shops with **CLOSER COMPETITORS** sell **MORE**.<br>
In this case, another certainty is contradicted. The fact that there is close competition helps the business outcome.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/hyp_2_distance.png)

**Hypothesis 07:**
Shops open during the Christmas holiday should sell more.<br>
**FALSE** - Shops open during the **CHRISTMAS HOLIDAY** sell **LESS**.<br>
Hypothesis 7 states that the shop opening on the Christmas holiday means selling more. However, the data shows that customer movement on holidays is lower and therefore the shop sells less.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/hyp_7_holiday.png)

**Hypothesis table:**
*The complete list of hypotheses is available in the project notebook.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/hypotheses_summary.png)


# 5. Machine Learning Model Applied
The following machine learning models were trained:

- Average model (reference);
- Linear Regression Model;
- Linear Regression Regularized Model - LASSO;
- Random Forest Regressor;
- XGBoost Regressor.

**All the models applied went through the Cross Validation stage.**

# 6. Machine Learning Model Performance
The following table shows the performance of the models after the "Cross-Validation" phase. Though the "Random Forest Regressor" model presented the best results, I used the "XGBoost Regressor" model for exploratory and hardware limitations reasons. 

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/ML_real_performance.png)

Thus, after choosing the final model, it is submitted in the fine-tuning phase results were positive and are below.

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/ML_xgb_fine_tuning.png)

# 7. Business Results

![Screenshot](https://github.com/egoliveira1/RossmannProject/blob/main/img/business_results.png)

# 8. Conclusions

# 9. Lessons Learned

# 10. Next Steps to Improve

# LICENSE

# All Rights Reserved - Comunidade DS 2021
