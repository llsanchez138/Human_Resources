# Human_Resources
Here contains the report for the Statistical Analysis on Human Resource Dataset 
Coding was completed in Python

2020 Human Resources Data Set 
Latosha Sanchez & Yue Qin

Summary 
Human resource management exists within every professional space to maintain a viable working environment. Understanding the performance of the employees can provide insight to how the company functions. Dr. Carla Patalano and Dr. Rich provided stimulation data for data scientists to explore and visualize data that could be important for the company and the employees.

Research Report 
Introduction 
For the final project, we analyzed the 2020 Human Resources Data Set. This dataset involves a simulation of 199 employees’ employment information and personal information. It consists of two tables: emp_info.csv and personal_info.csv.
As the name implies, the personal_info.csv table contains employees’ personal information. Through this table, we can access information such as an employee’s name (Employee Name), marital status (MarriedID), gender (GenderID), and location (State). The EmpID variable also allows us to connect this table to the emp_info.csv table in order to explore correlations between personal information and employment information.

Hypothesis Testing and Prediction Questions 
Since this dataset is a simulation of human resources data, we would like to explore whether there is any unfair treatment in this company. By joining the two tables together, we would be able to test potential association between variables. To address our question, we are most interested in variables which could possibly be correlated with pay rates.
To begin with, we would like to determine whether gender inequality exists in this company by examining the potential association between gender and pay rates. Therefore, our hypothesis testing question is whether the average pay rate of females is significantly lower than that of males. The null hypothesis for our question is “In the population, the distributions of the pay rates in the two groups (female & male) are the same. Any difference in the sample is due to chance.” Our alternative hypothesis is “In the population, the pay rates of females are lower, on average, than the pay rates of males.”

In order to better understand the distribution of pay rates, we want to determine whether employees’ special project counts can be used to predict their pay rates accurately. We will fit a linear regression model to these two variables and evaluate the performance of our model to determine whether a linear relationship is appropriate for the correlation between special project counts and pay rates.

Exploratory Data Analysis 
In this section, we will explore the 2020 Human Resource Data to test our hypothesis and identify any patterns for our prediction.
Table Requiring a Join Operation:
We begin the exploration of our data analysis by joining the tables personal_info and emp_info. The gender IDs are then replaced for their respective classification to reduce any confusion. This new table will be used to identify differences in pay rate based on an employee's gender for our hypothesis testing, as we will use this table to investigate if there is an association between the amount of special projects completed by each employee and their respective pay rate.

Aggregated Data Table:
We aggregate the selected_info table to view the gender counts for each position observed. This allows us to ensure the counts are comparable for our A/B test when comparing salary among Male and Female employees. Through the aggregation, we can see that the counts of Male and Female employees are comparable across the positions held.
Our alternative aims to identify if there are differences in the pay rates between two groups. As such, the next table is used to display the pay rate averages by gender. The information in the table will be important in our hypothesis testing, as we determine whether the difference between the two genders is significant.

Quantitative Plot:
To gain a brief overview of the variables in our prediction problem, we create a scatter plot depicting the relationship between special project counts and pay rates as our quantitative plot. The visualization of their association demonstrates that there might be a positive correlation between special project counts and pay rates for those plots with a non-zero special project count. Nonetheless, when it comes to employees with a zero special project count, the plots are not scattered and random enough, which implies that a linear regression model might not be a good fit. We will go into details later in the prediction section.
 

Qualitative Plot:
To ensure the genders are comparable for further analysis, we gather the counts of each gender by grouping them. The counts of each gender present in the selected_info table are displayed below. The bar chart confirms what we see above in the aggregated table, the counts are similar for each gender. This allows us to continue with A/B testing in our analysis and subsequently sets us up for our test statistic.

<img src= /Users/lsanchez/Desktop/Picture1.png />

Hypothesis Testing 
Null: In the population, the distribution of pay is the same between male and female employees. Any variation in the sample is due to chance.
Alternative:
In the population, there is a difference in the distribution of pay rate between male and female employees. In order to determine if the sample data provides sufficient data to accept or reject the null hypothesis, we must analyze the data and test the hypothesis. Due to the nature of our alternative hypothesis, our test statistic will be to identify the difference between the average pay for each of the two groups. Thus, we have chosen to use A/B Hypothesis Testing as our test method, which will allow us to differentiate genders under the distribution of the pay rate by comparing the difference of their means. Through the use of permutations we will obtain our p-value to ascertain the conclusion to either accept or reject the null hypothesis. We will be using a significance level of 0.05.
 

The P-Value is: 0.0354

Interpretation
After our distribution has been established we calculate the p-value, which is calculated by counting the values that fall under the alternative to evaluate the null. Thus, we find our p-value by counting the difference of means greater than or equal to the observed divided by the number of simulations we run.
As can be seen from our calculations, the p-value is less than our significance level of 0.05. We conclude that the data rejects the null hypothesis, thereby accepting the alternative that there is a difference between the pay rates among male and female employees from the given population.
Prediction 
After examining the association between gender and pay rates, we would like to delve into the question about what factors are correlated with pay rates. According to our previous quantitative plot, there seems to be a positive correlation between special project counts and pay rates. Therefore, we will try to fit a linear regression model to our human resources data in order to see whether special project counts can be used to make accurate predictions about employees’ pay rates. After fitting the linear regression model, we will analyze the residuals between actual pay rates and our predicted pay rates based on special project counts to evaluate whether it is appropriate to use a linear model to depict the relationship between these two variables.
# create the linear regression model and compute predicted pay rates 

# visualizes the residuals of the linear regression model
 

As our results show, there is a weak positive correlation between special project counts and pay rates (r = 0.4). The scatter plot of both the actual pay rates and the predicted pay rates based on special project counts demonstrates that our linear regression model’s performance varies for different special project counts. Specifically, we can evaluate our model’s performance using the plot of residuals. For employees with 2 or more special projects, the residuals of pay rates are scattered randomly above 0 and below 0, which shows no specific pattern. However, for employees with no special projects, the residuals between their actual pay rates and the predicted pay rates tend to be very large and also have a wide variation, which might explain why we got a relatively small correlation coefficient. In conclusion, our linear regression model is a good fit for employees with special projects, but not for those without any special projects. This is a reasonable result, as we may have to find other variables and models in order to predict the pay rates of employees who do not have any special projects.
Conclusion 
Our hypothesis was to find whether there was a difference in the pay rate of male and female employees, the alternative, or if they were the same, the null. Our A/B testing revealed a p-value of 0.03, which is less than our significance level of 0.05. Based on this we reject the null hypothesis that the difference in pay for the two genders are the same, accepting the alt that there is in fact a difference in pay between the two groups.
Meanwhile, under our predictions, we found a positive correlation of 0.4 between the pay rates and special project counts in the dataset, most notably for employees with two or more special projects.
We believe that the hypothesis and prediction method used was appropriate for what we were testing. A/B testing allowed us to adequately test the difference of means between the two groups.
There are limitations to this report that must be considered. In this analysis, we used data from the respondents of a singular company. This can cause a nonresponse bias. Further this provided a limited number of positions being evaluated and may not be representative of the general public. Rather than identifying which gender has the lesser pay rate, we instead focused on the general difference in the mean pay rate to remove any bias of the data when evaluating the difference between the two groups.
In the future, we think it would be beneficial to look at further predictions to see the correlation between pay rate and other factors, such as the employee performance score or employee satisfaction.
