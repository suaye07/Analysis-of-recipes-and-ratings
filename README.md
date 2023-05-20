# Data Analysis on the food receipes and ratings reviews since 2008

by Su Aye 

***Cooking Time and Average Rating Analysis***
---
## Introduction
In this project, I aim to investigate the relationship between cooking time and the average rating of recipes. The cooking time of a recipe is the duration it takes to prepare and cook the dish, while the average rating represents the overall satisfaction or quality of the recipe as rated by users. By analyzing this relationship, I can gain insights into whether cooking time influences the average rating of recipes.


### Analysis Question: What is the relationship between the cooking time and average rating of recipes?


---

## Cleaning and EDA

Before performing the analysis, I will clean and explore the dataset. This step involves preprocessing the data, handling missing values, and performing exploratory data analysis (EDA) to gain a better understanding of the variables involved. I will ensure the data is in a suitable format for further analysis.

***Data Cleaning***

***Univariate Analysis***

|   n_ingredients |   rating |
|----------------:|---------:|
|               1 |  4.30208 |
|               2 |  4.32877 |
|               3 |  4.44194 |
|               4 |  4.43527 |
|               5 |  4.39844 |

<iframe src="assets/Univariate_Analysis_1.html" width=600 height=400 frameBorder=0></iframe>

|   rating |   recipe_count |
|---------:|---------------:|
|        0 |          15035 |
|        1 |           2870 |
|        2 |           2368 |
|        3 |           7172 |
|        4 |          37307 |

<iframe src="assets/Univariate_Analysis_2.html" width=600 height=400 frameBorder=0></iframe>

***Bivariate Analysis***

<iframe src="assets/Bivariate_Analysis_1.html" width=600 height=400 frameBorder=0></iframe>
<iframe src="assets/Bivariate_Analysis_2.html" width=600 height=400 frameBorder=0></iframe>
<iframe src="assets/Bivariate_Analysis_3.html" width=600 height=400 frameBorder=0></iframe>

***Interesting Aggregates***

This agregates take the mean of the rating for each items and assign to the minutes that take each item to make and list it in an assencding order.

## First five rows from the sorted dataset.
| name                            |   mean_rating |   minutes |
|:--------------------------------|--------------:|----------:|
| vegan parmesan                  |           5   |         0 |
| southern comfort punch          |           2.5 |         1 |
| s o s dip  a k a dried beef dip |           5   |         1 |
| s o s   beverage                |           5   |         1 |
| russian root beer               |           4   |         1 |   

## Last five rows from the sorted dataset.

| name                      |   mean_rating |         minutes |
|:--------------------------|--------------:|----------------:|
| peach cordial             |             3 |  86415          |
| homemade vanilla extract  |             0 | 129600          |
| homemade vanilla          |             5 | 259205          |
| homemade fruit liquers    |             4 | 288000          |
| how to preserve a husband |             5 |      1.0512e+06 |

83627 rows × 2 columns

This another analysis put the category into the minutes it takes to make the food and calculate the mean of the rating for each category.

| cooking_time_category   |   mean_rating |
|:------------------------|--------------:|
| 0-30                    |       4.44887 |
| 30-60                   |       4.36716 |
| 60-90                   |       4.31028 |
| 90+                     |       4.22396 |

## Assessment of Missingness

In this phase, I will assess the missingness in the dataset, specifically focusing on the variables related to cooking time and average rating. I will investigate if there are any patterns or correlations between missing values and other variables. Various techniques such as visualization and statistical tests will be utilized to evaluate the missingness.

***NMAR Analysis***

***Missingness Dependency***
<iframe src="assets/Assessment_of_Missingness.html" width=600 height=400 frameBorder=0></iframe>

## Hypothesis Testing

To address my analysis question, "What is the relationship between the cooking time and average rating of recipes?", I will perform hypothesis testing. I will formulate appropriate null and alternative hypotheses and conduct statistical tests to determine if there is a significant relationship between cooking time and average rating. The results of the hypothesis testing will provide evidence for or against the existence of a relationship between these variables.

Null Hypothesis:The relationship between the cooking time and average rating of recipes is the greater the rating is the less cooking prep time to fullfill customer satisfaction.
Alternative Hypothesis: The relationship between the cooking time and average rating of recipes is the greater the rating is the more cooking prep time to prepare the better food.

Result: Correlation coefficient: -0.003993247071403871,
        P-value: 0.053182722882732604

Test Statistic: Mean Proportion of the cooking time and mean proportion of the rating
Siginificance level: 0.05
p-value: 0.05318
Conclusion: Since p-value is >0.05, we fail to reject the null hypothesis.

## Conclusion 

Based on the analysis and the obtained results, we fail to reject the null hypothesis. The null hypothesis states that the greater the rating is, the less cooking prep time required to fulfill customer satisfaction. However, we did not find sufficient evidence to support this claim.

The alternative hypothesis suggests that the greater the rating is, the more cooking prep time is needed to prepare better food. Although this alternative hypothesis was not directly tested, the lack of significant correlation between cooking time and average rating implies that there is no clear relationship supporting this claim.

In other words, the analysis did not find a strong linear relationship between cooking time and average rating. The correlation coefficient was found to be approximately -0.004, which is very close to zero. This indicates a weak or negligible linear relationship between the two variables.

Therefore, based on the analysis, we cannot conclude that there is a significant relationship between cooking time and average rating of recipes. Other factors, such as recipe quality, ingredients, or cooking techniques, may have a stronger influence on the average rating of recipes rather than just the cooking time alone.

By conducting the above steps, I aim to gain insights into the relationship between cooking time and the average rating of recipes. The findings from this analysis help me understand whether cooking time plays a role in determining the quality or satisfaction of recipes.
