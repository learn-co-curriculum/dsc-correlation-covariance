
# Covariance and Correlation

In this lesson we shall look at **Covariance** and **Correlation** as two key concepts in the field of probability and statistics. Both of these concepts are used to describe the relationship between two variables to each other. Also, both are tools of measurement of **dependence** between variables.

## Objectives

You will be able to

* Understand and calculate covariance between given variables
* Understand and calculate correlation between variables
* Visualize and interpret the results of Pearson correlation coefficient  



### Introduction to Covariance 

>In stats, If you are trying to figure out how two random variables tend to **vary** together, you are effectively talking about **Covariance** between these variables. 

Covariance is used to measure **how much variables change *together* **, and it is calculated using the formula:

![](co-variance.jpg)




IF X and Y are two random variables having n variables, then 
```
Xi = ith element of variable x
Yi = ith element of variable y
n = number of data points (these must be same in X and Y)
mu_x = the mean of the independent variable x
mu_y = the mean of the dependent variable y

sigma(xy) = Calculated covariance
```

Note: For sample correlation , we divide by (n-1) due to the principle called Bessel's correction. [Here is a mathematical proof for this.](https://lazyprogrammer.me/covariance-matrix-divide-by-n-or-n-1/). We shall visit this point again later in the course to see its impact on the outcome. A general proof for covariance is available [here](https://math.tutorvista.com/statistics/covariance.html)

### Interpreting Covariance values 

* A positive covariance indicates that **higher than average** values of one variable tend to be paired with higher than average values of the other variable. 
* Negative covariance indicates that higher than average values of one variable tend to be paired with **lower than average** values of the other variable. 
* a zero value, or values close to zero indicate no covariance, i.e. no values from one variable can be paired with values of second variable. 

This behavior can be further explained using the scatter plots below
![](https://www.statisticshowto.datasciencecentral.com/wp-content/uploads/2013/12/g-covariance.gif)





A large negative covariance value show an inverse relationship between values at x and y axes. i.e. y decreases as x increases. This is shown by the scatter plot on the left. 

The middle scatter plot shows values spread all over the plot, reflecting the fact that variables on x and y axes can not be related in terms of how they vary together. The covariance value for such variables would be very close to zero. 

In the scatter plot on right, we see a strong relationship between values at x and y axes i.e. y increases as x increases. 

>Covariance is not standardized, unlike the correlation. Therefore, covariance values can range from negative infinity to positive infinity.

### Introduction to Correlation

>When two random variables **correlate**, this reflects that the change in one item **effects** the change in the values of second variable. 

Correlation is a bivariate analysis that measures the strength of association between two variables and the direction of the relationship. In statistics, we measure four types of correlations for detailed relationship analysis: Pearson correlation, Kendall rank correlation, Spearman correlation, and the Point-Biserial correlation. For this lesson, we shall focus on Pearson correlation as it is the go-to correlation measure for most needs. 

Pearson Correlation (r) is calculated using following formula :
![](correlation.png)



Here x and y are the random variables, x_bar and y_bar are the mean values for both x and y. A detailed mathematical insight into this equation is available [in this paper](http://www.hep.ph.ic.ac.uk/~hallg/UG_2015/Pearsons.pdf)

### Interpreting Correlation values

>Correlation formula shown above always gives values in a range between -1 and 1. 

For example, if two variables have a correlation of +0.9,  this means the change in one item results in an almost similar change to another item. A correlation value of -0.9 means that the change is one variable results as an opposite change in the other variable. A pearson correlation near 0 would be no effect. Here are some example of pearson correlation calculations as scatter plots. 
![](https://statistics.laerd.com/statistical-guides/img/pearson-2-small.png)

Think about stock markets in terms of correlation. All the stock market indexes tend to move together in similar directions. When the DOW Jones loses 5%, the S&P 500 usually loses around 5%. When the DOW Jones gains 5%, the S&P 500 usually gains around 5% because they are **highly correlated**.

On the other hand, there could also be negative correlation where you might observe that as the DOW Jones loses 5% of it value, Gold might gain 5%. Alternatively, if the Dow Jones gains 5% of its value, Gold may lose 5% of its value. That's **negative correlation**. 

### So how do these measures relate to each other ?

Both covariance and correlation have their own applications. Covariance can be classified as positive  when two variables tend to vary together, and negative when one variable is above or below the expected value compared to another variable. 

Correlation has three categories; positive, negative, or zero and shows the effect of change of one variable on another. 

An obvious difference between the two is that correlation is dimensionless where covariance is in units of variables. Covariance focuses the relationship of only two entities such as variables of sets of data. In contrast, correlation can involve multiple variables or data sets and their relationships. 

The correlation coefficient is a function of the covariance. The correlation coefficient is equal to the covariance divided by the product of the standard deviations of the variables. Therefore, a positive covariance always results in a positive correlation and a negative covariance always results in a negative correlation.

Here is a fun fact for you highlighting that "Correlation isn't Causation". But this one seems like an exception .. what do you think ?


![](http://www.tylervigen.com/chart-pngs/2.png)

## Summary
This lesson explains the calculations for covariance and correlation and how to interpret the values for both of these. We learnt to measure and represent how strongly two random variables as correlation. Correlation refers to the scaled form of covariance.

>Correlation is dimensionless, i.e. it is a unit-free measure of the relationship between variables. Covariance is a measure of correlation.
