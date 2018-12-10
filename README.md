
# Understanding Covariance and Correlation

## Introduction 

In this lesson, we shall look at how **Variance** of a random variable is used to calculate **Covariance** and **Correlation**, two key measures used in Statistics for finding the relationships between random variables. These measures help us identify the degree to which two sets of data tend to deviate from their expected value (i.e. mean), __in a similar way__. Based on these measures, we can identify if two variable are dependent on each other, and to what extend. This lesson will help you develop a conceptual understanding, necessary calculations and some precautions while using these measures. 

## Objectives

You will be able to

* Understand and explain data variance and how it relates to standard deviation
* Understand and calculate Covariance and Correlation between two random variables
* Visualize and interpret the results of Covariance and Correlation
* Explain what is meant by the popular term "Correlation does not imply Correlation"


## Revisiting Variance ($\sigma^2$)

Earlier in the course, we introduced __Variance__ (represented by $\sigma^2$) as a measure of dispersion for continuous random variables. Let's quickly revisit this, as variance formula plays a key role while calculating Covariance and Correlation measures.

> __Variance is a measure used to quantify how much a random variable deviates from its mean value__. 

When we calculate variance, we are essentially asking, "__Given the relationship of all given data points, how much distant from mean do we expect the next data point to be?__"  This "distance" is called the **error term**, and it's what variance is measuring. 

### Calculating Variance 

We introduced the formula for calculating variance as shown below:

$$\sigma^2 = \frac{\sum(x-\mu)^2}{n}$$

- $x$ represents an individual data points
- $\mu$ is the mean of the data points. 
- $n$ is the total number of data points. 

*While calculating a sample variance in order to estimate a population variance, the denominator of the variance equation becomes n - 1. This removes bias from the estimation, as it prohibits the researcher from underestimating the population variance.*

Following illustration summarizes how spread of data around mean (10) relates to the variance for different variables. In general, you would notice that higher variance simply relates to a larger spread of the distribution of observations around the mean value. 

<img src="var2.png" width=500>


Let's take this further and see how this relates to __Covariance__. 


## Covariance ($\sigma_{xy}$)

Now that we know what variance and what quantity it measures, imagine calculating variance of two random variables to get some idea on how they change together (or stay the same) considering all values for both variables.

In Stats, when we try to figure out how two random variables tend to **vary** together, we are effectively talking about **Covariance** between these variables. Covariance provides an insight into how two variables are __related__ to one another. 

More precisely, covariance refers to:

> The measure of how two random variables in a data set will __change together__. 

It measures whether the two move in the same direction (a positive covariance) or in opposite directions (a negative covariance).



### Example Use Cases

Covariance (and correlation, as we shall see later) is a common technique used in multiple areas of machine learning.

A key application of covariance is to check for the extent of linear relationship between two variables. A positive covariance means that the two variables at hand are positively related, and they move in the same direction, whereas a negative covariance means that the variables are inversely related, or that they move in opposite directions. A zero value of covariance would effectively highlight "no linear relation". This forms the foundations for regression analysis as we shall see later. 

Covariance calculation plays a major role in a number of advanced machine learning algorithms in dimensionality reduction and predictive analyses. In a business context, risk management and aversion practices and related techniques rely heavily upon covariance. 

### How to calculate Covariance ?
In essence, we use covariance to measure **how much variables change *together* **, and it is calculated using the formula:


$$\sigma_{XY} = \frac{\sum_{i=1}^{n}(x_i -\mu_x)(y_i - \mu_y)}{n}$$

Here $X$ and $Y$ are two random variables having n elements each. We want to caluclate ___how much $Y$ depends on $X$___ (or vice-versa), by measuring how values in $Y$ change with observed changes in $X$ values. 

> This makes $X$ our __independent variable__ and $Y$, the __dependent variable__.  

$x_i$ = ith element of variable $X$

$y_i$ = ith element of variable $Y$

$n$ = number of data points (__$n$ must be same for $X$ and $Y$__)

$\mu_x$ = mean of the independent variable $X$

$\mu_y$ = mean of the dependent variable $Y$

$\sigma_{XY}$ = Covariance between $X$ and $Y$

*We can see that above formula calculates the variance of $X$ and $Y$ (check the variance formula above) by multiplying the variance of each of their corresponding elements. Hence the term __Co-Variance__.*

A general proof for covariance is available [here](https://math.tutorvista.com/statistics/covariance.html)*

### Interpreting Covariance values 

* A positive covariance indicates that **higher than average** values of one variable tend to pair with higher than average values of the other variable.

* Negative covariance indicates that higher than average values of one variable tend to pair with **lower than average** values of the other variable. 

* a zero value, or values close to zero indicate no covariance, i.e. no values from one variable can be paired with values of second variable. 

This behavior can be further explained using the scatter plots below:

<img src="cov22.png" >





In the left image above, we see that x and y tend to increase together, i.e. stock market returns increase with an increase in economic growth. These two variable has a positive covariance i.e. one increases with an increase in the other. 

In the right image, a negative covariance exists between "Gasoline Price" and "World Oil Population". This reflects the fact that gas price tends to decrease as a result of population increase. This is shown as an inverse relationship between values at x and y axes. i.e. y decreases as x increases. This is shown by the scatter plot on the left. 

In the absence of negative or positive covariance , there will not be a linear pattern present as we see in above examples. A pattern-less spread of data reflects no (or close to zero) covariance.


>__Covariance is not standardized. Therefore, covariance values can range from negative infinity to positive infinity.__

## Correlation 

Above, we saw how covariance can identify the degree to which two random variables tend to vary together, while using a formulation that depends on the units of $X$ and $Y$ variables. During data analysis, covariance measure can not be directly used in data comparison as it different experiments may contain underlying data measured in different units. For this, we need to normalize this degree of variation into a standard unit, with interpretable results independent of the units of data. We achieve this with a derived normalized measure, called correlation. 

__Correlation is defined as covariance, normalized by the square rooted product of standard deviations of $X$ and $y$. This normalization helps us set the scale from 0 to 1.__ So the correlation between 𝑋 and 𝑌 would be calculated as:

$$Correlation(X,Y) = \frac{\sigma_{X,Y}}{\sqrt{\sigma_X\sigma_Y}}$$

>When two random variables **Correlate**, this reflects that the change in one item **effects** the change in the values of second variable. 

In data science practice, we typically to look at correlation rather than covariance when comparing variables. Correlation is more interpretable, since it does not depend on the scale of either random variable involved.


### Use Cases

The correlation measure can be used in a number of analytical contexts as highlighted below:

#### Social Media and Websites
Digital publishers want to maximize their understanding of the potential relationship between social media activity and visits to their website. For example, a digital publisher may run a correlation report between __hourly Twitter mentions__ and __website visits__ for a given time period. The correlation can be used to identify relationship between these two variables. This may help develop improved digital marketing and commerce strategies. 

#### Optimization for E-retailers

Online retailers are always interested in driving increased revenue. An e-retailer may want to compare a number of secondary success events (e.g., file downloads, product detail page views, internal search click-throughs, etc.) with weekly web revenue. They can quickly identify internal search click-throughs as having the highest correlation, which may indicate an area for optimization.

### Types of Correlation Measures

__Coefficient of correlation__, r, called the linear correlation coefficient, measures the strength and the direction of a linear relationship between two variables. It also called as __Pearson correlation coefficient__. 

In statistics, we measure four types of correlations for detailed relationship analysis: 
* Pearson correlation 
* Kendall Rank correlation 
* Spearman correlation
* Point-Biserial correlation. 


For now, we shall focus on __Pearson correlation__ as it is the go-to correlation measure for most needs. 

Pearson __r__ correlation is the most widely used correlation statistic to measure the degree of the relationship between two linearly related variables. For the Pearson r correlation, both variables should be normally distributed (normally distributed variables have a bell-shaped curve). Other assumptions include linearity and homoscedasticity. Linearity assumes a straight line relationship between each of the two variables and homoscedasticity assumes that data is equally distributed about the regression line.


### Calculating Coefficient of Correlation (r)

Pearson Correlation (r) is calculated using following formula :

$$ r = \frac{\sum_{i=1}^{n}(x_i -\mu_x)(y_i - \mu_y)} {\sqrt{\sum_{i=1}^{n}(x_i - \mu_x)^2 \sum_{i=1}^{n}(y_i-\mu_y)^2}}$$

So just like in the case of covariance,  $X$ and $Y$ are two random variables having n elements each. 


$xi$ = ith element of variable $X$

$yi$ = ith element of variable $Y$

$n$ = number of data points (__$n$ must be same for $X$ and $Y$__)

$\mu_x$ = mean of the independent variable $X$

$\mu_y$ = mean of the dependent variable $Y$

$r$ = Calculated Pearson Correlation


*A detailed mathematical insight into this equation is available [in this paper](http://www.hep.ph.ic.ac.uk/~hallg/UG_2015/Pearsons.pdf)*

### Interpreting Correlation values

> __Correlation formula shown above always gives values in a range between -1 and 1__

If two variables have a correlation of +0.9,  this means the change in one item results in an almost similar change to another item. A correlation value of -0.9 means that the change is one variable results as an opposite change in the other variable. A pearson correlation near 0 would be no effect. Here are some example of pearson correlation calculations as scatter plots. 

![](correx.svg)

Think about stock markets in terms of correlation. All the stock market indexes tend to move together in similar directions. When the DOW Jones loses 5%, the S&P 500 usually loses around 5%. When the DOW Jones gains 5%, the S&P 500 usually gains around 5% because they are **highly correlated**.

On the other hand, there could also be negative correlation where you might observe that as the DOW Jones loses 5% of it value, Gold might gain 5%. Alternatively, if the Dow Jones gains 5% of its value, Gold may lose 5% of its value. That's **negative correlation**. 

### So how do these measures relate to each other ?

Are Covariance and Correlation The Same Thing? Simply put, no.

- __While both covariance and correlation indicate whether variables are positively or inversely related to each other, they are not considered to be the same.__ 

This is because correlation also informs about the degree to which the variables tend to move together. 

- __Covariance is used to measure variables that have different units of measurement.__ 

By leveraging covariance, analysts are able to determine whether units are increasing or decreasing, but they are unable to solidify the degree to which the variables are moving together due to the fact that covariance does not use one standardized unit of measurement.

- __Correlation standardizes the measure of interdependence between two variables and informs researchers as to how closely the two variables move together.__

## Correlation is not Causation

A lot of times we have heard __“correlation is not causation”__ or __“correlation does not imply causation”__ . But what do we mean by saying this?

Causation takes a step further than correlation. It says:
> Any change in the value of one variable will cause a change in the value of another variable, which means one variable makes other to happen. It is also referred as __cause and effect__.

__Example__: When a person is exercising then the amount of calories burning goes up every minute. Former is causing latter to happen. So now we know what correlation and causation is, it’s time to understand “ __Correlation does not imply causation!__” with a famous example.

### "Ice cream sales is correlated with number of homicides in New York" 

### Considering the Hidden Factors

In some cases there are some hidden factors which are related on some level. Like in our example of ice cream sales and homicide rates , weather is the hidden factor which is causing both events. Weather is actually causing the rise in ice cream sales and homicides. As in summer people usually go out, enjoy nice sunny day and chill themselves with ice creams. So when it’s sunny, wide range of people are outside and there is a wider selection of victims for predators. There is no causal relationship between the ice cream and rate of homicide, sunny weather is bringing both the factors together. We can say that ice cream sales and homicide rate have a __causal relationship__ with weather.

This is reflected in the image below:

<img src="cc.png" width=300>

Just after finding correlation, we shouldn't draw the conclusion too quickly. Instead we should take time to find other underlying factors as correlation is just the first step. Find the hidden factors, verify if they are correct and then conclude.


Here is some more (rather funny examples) of how correlation analysis may lead to inconceivable findings.

#### Divorce rate correlates with margarine consumption 

<img src="divorce.png" width=600>


#### Cheese consumption correlates with Engineering doctorates


<img src="cheese.png" width=600>

#### Number of Nicholas Cage movie releases correlates with people drowning in pools


<img src="cage.png" width=600>


Internet is full of other funny correlations, do a quick Google search and you'll come across lots of them. So the key takeaway here is that covariance and correlation analysis should be used with care. A high correlation may indicate some sort of __casual relationship__ between variables. It should not be taken as a __cause-effect__ 
scenario. 

<img src="joke.png" width=600>


---

**IMPORTANT NOTE:** The variance formula above considers $X$ and $Y$ to be population variables.  For samples , we divide by (n-1), instead of n due to the principle called Bessel's correction. [Here is a mathematical proof for this.](https://lazyprogrammer.me/covariance-matrix-divide-by-n-or-n-1/). We shall visit this point again later in the course to explore it in greater details. 

## Summary
In this lesson, we looked at Identifying the variance of random variables as a measure of mean deviation. We saw how this measure can be used to first calculate covariance, followed by the correlation to analyze how change variable effects the change of another variable. We looked at the formulas for calculating these measures and you are provided with mathematical proofs of these formulas. Next, we shall see how we can use correlation analysis to run a __regression analysis__ and later, how covariance calculation helps us with dimensionality reduction. 

#### Key Takeaways
- Correlation is dimensionless, i.e. it is a unit-free measure of the relationship between variables. 
- Correlation is a normalized form of covariance and exists between [0,1]
- Correlation is not Causation
