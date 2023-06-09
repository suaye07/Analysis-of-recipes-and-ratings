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

First I perform data cleaning and merging of two datasets, 'raw_interactions' and 'raw_recipes', to create a combined dataset named 'combined'. In the first step, the code merges the two datasets based on the common 'recipe_id' column, removing the duplicate 'id' column in the process. Next, the code handles data quality issues by converting the 'rating' column values to NaN (missing values) if they are equal to "0". This is done using a lambda function applied to the 'rating' column. After the data cleaning, the code proceeds to merge the 'combined' dataset with the 'average_rating_per_recipe' dataset. This step adds the average rating information for each recipe based on the 'recipe_id' column.
Finally, unnecessary columns are dropped, and the 'rating_y' column is renamed to 'mean_rating' to improve clarity. The resulting dataset, named 'merged_data', is now ready for further analysis and exploration of the relationship between recipe attributes and average ratings.
Overall, this data cleaning process ensures data integrity, handles missing values, and combines relevant information from multiple datasets, setting the foundation for accurate and comprehensive analysis.
From this cleaned data, I perform the below analysis to explore relationships, patterns, and characteristics of the dataset, providing a comprehensive understanding of the data and facilitating further insights and decision-making.

***Univariate Analysis***

This analysis performs a univariate analysis on the 'rating' column. It calculates the average rating per recipe based on the number of ingredients and creates a histogram to visualize the distribution of these average ratings. This analysis allows you to understand the relationship between the number of ingredients and the average rating of recipes. The resulting histogram provides insights into the distribution of average ratings.

|   n_ingredients |   rating |
|----------------:|---------:|
|               1 |  4.30208 |
|               2 |  4.32877 |
|               3 |  4.44194 |
|               4 |  4.43527 |
|               5 |  4.39844 |

<iframe src="assets/Univariate_Analysis_1.html" width=600 height=400 frameBorder=0></iframe>

This second analysis a univariate analysis on the 'rating' column. It calculates the count of recipes for each rating and creates a pie chart to visualize the distribution of these counts. This analysis allows you to understand the distribution of recipe counts across different ratings. The resulting pie chart provides a visual representation of this distribution.

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
Correlation coefficient between Cooking Time and Average Rating: -0.00399
A negative correlation coefficient shows an inverse relationship between the two variables being analyzed. In this analysis between cooking time and average rating of recipes, a negative correlation coefficient suggests that as the cooking time increases, the average rating tends to decrease, and vice versa. However, it's -0.00399 which indicates the very less impact between this two cooking time and rating correlation interact.

<iframe src="assets/Bivariate_Analysis_2.html" width=600 height=400 frameBorder=0></iframe>
Correlation coefficient between Cooking Time and Steps to make: 0.01169
This also indicates a very weak positive correlation. Overall, the analysis suggests a negligible relationship between cooking time and the number of steps to make in the dataset.


<iframe src="assets/Bivariate_Analysis_3.html" width=800 height=500 frameBorder=0></iframe>
This analysis is to identify the top-rated recipes with a rating of 5, cooking time less than 20 minutes, and submitted after January 1, 2018. It then creates a horizontal bar plot to compare the cooking time and number of steps for these recipes.
The purpose of this analysis is to identify highly rated recipes that require a short cooking time. By focusing on recipes with a rating of 5 and a cooking time less than 20 minutes, you can find quick and well-received recipes. Additionally, by considering recipes submitted after January 1, 2018, you narrow down the analysis to more recent recipes.
The resulting bar plot allows for a visual comparison of the cooking time and number of steps for each recipe. This helps identify recipes that achieve a high rating with minimal cooking time and a simple preparation process.
Overall, this analysis aims to provide insights into top-rated, quick-to-make recipes, helping users find appealing options that require minimal time and effort in the kitchen.

***Interesting Aggregates***

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

This agregates take the mean of the rating for each items and assign to the minutes that take each item to make and list it in an assencding order. The purpose of this analysis is to gain insights into the relationship between cooking time and the average rating of recipes. By grouping the data by recipe name and calculating the average cooking time and mean rating, you can examine how these variables vary across different recipes. The pivot table provides a concise summary of the aggregate statistics, allowing for easy comparison and identification of recipes with shorter or longer cooking times and their corresponding average ratings.

| cooking_time_category   |   mean_rating |
|:------------------------|--------------:|
| 0-30                    |       4.44887 |
| 30-60                   |       4.36716 |
| 60-90                   |       4.31028 |
| 90+                     |       4.22396 |

This another analysis put the category into the minutes it takes to make the food and calculate the mean of the rating for each category. The purpose of this analysis is to examine the relationship between cooking time and average rating, grouped into different time categories. By categorizing the recipes based on cooking time intervals (0-30 minutes, 30-60 minutes, 60-90 minutes, and 90+ minutes), you can explore whether there are any patterns or trends in the average ratings across these categories.

Overall, this analysis helps understand if there is any correlation between cooking time and the average rating of recipes, enabling you to identify potential trends or preferences among users based on different cooking time categories.

## Assessment of Missingness

In this phase, I will assess the missingness in the dataset, specifically focusing on the variables related to cooking time and average rating. I will investigate if there are any patterns or correlations between missing values and other variables. Various techniques such as visualization and statistical tests will be utilized to evaluate the missingness.


***NMAR Analysis***

I believe minutes column, the cooking time in minutes might likely be fall into NMAR category. It is possible that recipes with longer cooking times might have a higher chance of missing ratings or reviews. For example, users may be less inclined to review or rate recipes that require a longer time investment.
To determine if the missingness in the "mean_rating" column is NMAR, additional data such as user demographics, recipe complexity, or user engagement metrics could be useful. These variables might help explain the missingness pattern and shed light on whether it is related to the missing ratings themselves or to other unobserved factors.
It is important to conduct further analysis and investigate the relationship between the missingness and potential explanatory variables to determine if the missingness in the "mean_rating" column is truly NMAR or if it can be explained by other factors, making it MAR (Missing at Random) or MCAR (Missing Completely at Random).

***Missingness Dependency***


<iframe src="assets/Assessment_of_Missingness.html" width=600 height=400 frameBorder=0></iframe>
p-value: 0.07

The purpose of this analysis is to explore whether the missingness of the 'description' column is related to the values in the 'n_steps' column. By examining the distribution of missing and non-missing values in the 'description' column for different groups of 'n_steps', we can assess if there is a systematic relationship between these variables. A permutation test is performed by randomly shuffling the 'n_steps' variable and computing the total variation distance (TVD) between the shuffled and original distributions. This process is repeated multiple times to create a null distribution of TVD values. The observed TVD from the original data is compared to the null distribution to compute a p-value, indicating the likelihood of observing such or more extreme TVD values under the null hypothesis of no association.

Analysis: Since p-value of 0.07, it means that there is a 7% chance of observing the observed total variation distance (TVD) or a more extreme TVD under the null hypothesis of no association between the 'n_steps' variable and the missingness of the 'description' column. This suggests that there is not strong enough evidence to conclude a significant association between the 'n_steps' variable and the missingness of the 'description' column. However, it is worth noting that the interpretation of p-values can also depend on the specific context and the desired level of significance for the analysis.

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
