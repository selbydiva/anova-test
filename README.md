# Anova Test

In this section, we will discuss how to find the correlation between categorical and continuous variables using the ANOVA test.

Here's the data we have, our objective is to determine whether there is a strong correlation between genre and rating.

<img width="841" alt="Anova-1" src="https://github.com/selbydiva/anova-test/assets/154320650/86fa3a07-fbb1-4a62-8d12-79fa971dd493">

We will compute correlations using both Python and manual methods (by hand).

# Using Python

In Python, we can easily run an ANOVA test using the statsmodels.api library and the anova_lm function.

<img width="486" alt="Screenshot 2024-07-07 at 17 18 30" src="https://github.com/selbydiva/anova-test/assets/154320650/781c9243-4872-4cba-9670-55f53038efc8">

First, we will employ the Ordinary Least Squares (OLS) regression by utilizing the `ols` function from the `statsmodels` library in Python to establish the relationship between the genre and rating variables.

Next, we will utilize the `anova_lm` function from the `statsmodels.api` library to obtain a summary of key information, particularly the F-value and P-Value. These F-value and P-value are crucial for assessing the significance of the relationship between these two variables.


- If the P-value is less than the significance level, we reject the null hypothesis, indicating a significant correlation between the variables.<br>
- If the P-value is greater than or equal to the significance level, we fail to reject the null hypothesis, suggesting no significant correlation between the variables.

In this case, the p-value is 0.025835, which is less than the significance level of 0.05. Therefore, we can conclude that there is a significant correlation between the genre and rating.

# Manually (by hand)

To simplify the manual calculations, it's better to organize the data into three columns, each representing a group: 'Romance', 'Horror', and 'Comedy'. Below is an ANOVA table that we need to complete.

<img width="476" alt="Anova-9" src="https://github.com/selbydiva/anova-test/assets/154320650/96af1c33-63fc-4934-bd70-ceb318d6dbef">

**Step 1: Calculate Sum of Squares Regression (SSR) – Between Groups**

Sum of Squares Regression measures the variability between group averages and the grand average. To compute this, we first find the average for each group and the grand average of all the data.

<img width="1438" alt="Anova-3" src="https://github.com/selbydiva/anova-test/assets/154320650/4ada63f7-aa5f-4ffc-b99a-2c735689560a">

<img width="1436" alt="Anova-4" src="https://github.com/selbydiva/anova-test/assets/154320650/c9a63d25-0b07-4768-a7b0-a52b49b273df">

**Step 2: Calculate Sum of Squares Error (SSE) – Within Groups**

Sum of Squares Error measures the variability within each group. It quantifies how much the individual observations within each group deviate from their respective group means. To compute this, we subtract each data point from the corresponding group average and then square the result.

<img width="1436" alt="Anova-5" src="https://github.com/selbydiva/anova-test/assets/154320650/003de71b-2302-4058-a338-7559cd45c6cd">

Let's put  the SSR and SSE values in the ANOVA table.

<img width="1318" alt="Anova-6" src="https://github.com/selbydiva/anova-test/assets/154320650/a54d03f9-9e6f-43ba-869c-17a2cf2271b7">

**Step 3: Calculate Degrees of Freedom and F-Value**

We then find the degrees of freedom using the appropriate formulas. The F-Value is calculated by dividing each sum of squares by its corresponding degrees of freedom.

<img width="1438" alt="Anova-7" src="https://github.com/selbydiva/anova-test/assets/154320650/9a30af49-79cf-4fa2-9826-199020081cb5">

**Step 4: Determine Significance Using the F-Value**

To conclude whether the genre and rating variables are significant, we compare the calculated F-Value with the critical F-value obtained from an F-table, based on the degrees of freedom.

<img width="1435" alt="Anova-8" src="https://github.com/selbydiva/anova-test/assets/154320650/c4f104c9-6f76-4cfb-a8c1-c9b495577f0b">

- If the F-Value is greater than or equal to the critical F-value, we reject the null hypothesis, indicating a significant correlation between the variables.<br>
- If the F-Value is less than the critical F-value, we fail to reject the null hypothesis, suggesting no significant correlation between the variables.

In this case, the critical F-value is 5.14, which is less than the calculated F-Value of 7.1468. Therefore, we reject the null hypothesis, indicating a significant correlation between the genre and rating variables.









