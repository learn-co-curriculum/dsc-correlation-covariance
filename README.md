
# Understanding Covariance and Correlation

## Introduction 

In this lesson, we shall look at how **Variance** of a random variable is used to calculate **Covariance** and **Correlation** as key measures used in Statistics for finding casual relationships between random variables. Based on these measures, we can identify if two variable are associated each other, and to what extend. This lesson will help you develop a conceptual understanding, necessary calculations and some precautions while using these measures. 

## Objectives

You will be able to

* Understand and calculate Covariance and Correlation between two random variables
* Visualize and interpret the results of Covariance and Correlation
* Explain what is meant by the popular phrase "Correlation does not imply Correlation"

## Variance ($\sigma^2$)

Earlier in the course, we introduced __Variance__ (represented by $\sigma^2$) as a measure of dispersion for continuous random variables from its expected mean value. Let's quickly revisit this, as variance formula plays a key role while calculating Covariance and Correlation measures.

The formula for calculating variance as shown below:

$$\sigma^2 = \frac{\sum_{i=1}^{n}(x_i-\mu)^2}{n}$$

- $x$ represents an individual data points
- $\mu$ is the mean of the data points. 
- $n$ is the total number of data points. 

Let's take this further and see how this relates to __Covariance__. 


## Covariance ($\sigma_{xy}$)

Imagine calculating variance of two random variables to get an idea on how they change together considering all values for both variables. In Stats, when we try to figure out how two random variables tend to **vary together**, we are effectively talking about **Covariance** between these variables, which helps us identify how two variables are __related__ to one another. 

As we will see later in the course, Covariance calculation plays a major role in a number of advanced machine learning algorithms like dimensionality reduction and predictive analyses etc.

### Calculating Covariance ?
If we have $X$ and $Y$, two random variables having $n$ elements each. We can to calculate covariance between these two variables, by measuring how values in $Y$ change with observed changes in $X$ values with the formula below. 


$$\sigma_{XY} = \frac{\sum_{i=1}^{n}(x_i -\mu_x)(y_i - \mu_y)}{n}$$

- $\sigma_{XY}$ = Covariance between $X$ and $Y$
- $x_i$ = ith element of variable $X$
- $y_i$ = ith element of variable $Y$
- $n$ = number of data points (__$n$ must be same for $X$ and $Y$__)
- $\mu_x$ = mean of the independent variable $X$
- $\mu_y$ = mean of the dependent variable $Y$


> *We see that above formula calculates the variance of $X$ and $Y$ by multiplying the variance of each of their corresponding elements. Hence the term __Co-Variance__.*

A general proof for covariance is available [here](https://math.tutorvista.com/statistics/covariance.html)*

### Interpreting Covariance values 

Covariance values range from positive infinity to negative infinity. 


* A positive covariance indicates that **higher than average** values of one variable tend to pair with higher than average values of the other variable.

* Negative covariance indicates that higher than average values of one variable tend to pair with **lower than average** values of the other variable. 

* a zero value, or values close to zero indicate no covariance, i.e. no values from one variable can be paired with values of second variable. 


The main shortcoming of covariance is that it keeps the scale of the variables $X$ and $Y$, and therefore can take on any value between positive and negative infinity. This makes interpretation difficult and comparing covariances to each other impossible. For example, $Covariance(a, b)  = 3.6$ and $Covariance(p, q) = 9$ tell us that these pairs are positively associated, but it is difficult to tell whether the relationship between a and b is stronger than p and q without looking at the means and distributions of these variables.

This is where we need correlation.  

> __Correlation is calculated by standardizing covariance by some measure of variability in the data, it produces a quantity that has intuitive interpretations and consistent scale.__

## Correlation

We have seen that covariance uses a formulation that depends solely on the units of $X$ and $Y$ variables. During data analysis, often covariance measure can not be directly used as different experiments may contain underlying data measured in different units. For this, we need to normalize this degree of variation into a standard unit, with interpretable results,  __independent of the units of data__. We achieve this with a derived normalized measure, called __Correlation__. 

The term "correlation" refers to a casual relationship or association between variables. In almost any business, it is useful to express one quantity in terms of its relationship with others. For example: 
- Sales might increase when the marketing department spends more on TV advertisements
- Customer's average purchase amount on an e-commerce website might depend on a number of factors related to that customer, e.g. location, age group, gender etc.
- Social media activity and website clicks might be be associated with revenue that a digital publisher makes. etc.

Correlation is the first step to understanding these relationships and subsequently building better business and statistical models.

>When two random variables **Correlate**, this reflects that the change in one item has some **measureable effect** on the change in the values of second variable. 


*In data science practice, while checking for associations between variables, we typically look at correlation rather than covariance when comparing variables. Correlation is more interpretable, since it does not depend on the scale of either random variable involved*.




### Pearson's Correlation Coefficient $r$

__Pearson Correlation Coefficient__, $r$, also called the __linear correlation coefficient__, measures the strength and the direction of a __linear relationship__ between two variables. This coefficient quantifies the degree to which a relationship between two variables can be described by a line. 

*Note: There are a [number other correlation coefficients](https://math.tutorvista.com/statistics/correlation.html),  but for now, we shall focus on __Pearson correlation__ as it is the go-to correlation measure for most needs. *




### Calculating Correlation Coefficient

Pearson Correlation (r) is calculated using following formula :

$$ r = \frac{\sum_{i=1}^{n}(x_i -\mu_x)(y_i - \mu_y)} {\sqrt{\sum_{i=1}^{n}(x_i - \mu_x)^2 \sum_{i=1}^{n}(y_i-\mu_y)^2}}$$

So just like in the case of covariance,  $X$ and $Y$ are two random variables having n elements each. 


- $xi$ = ith element of variable $X$
- $yi$ = ith element of variable $Y$
- $n$ = number of data points (__$n$ must be same for $X$ and $Y$__)
- $\mu_x$ = mean of the independent variable $X$
- $\mu_y$ = mean of the dependent variable $Y$
- $r$ = Calculated Pearson Correlation


*In terms of variance , we can see that we are effectively measuring the variance of both of both variables together, normalized by their standard deviations. A detailed mathematical insight into this equation is available [in this paper](http://www.hep.ph.ic.ac.uk/~hallg/UG_2015/Pearsons.pdf)*

### Interpreting Correlation values

> __Correlation formula shown above always gives values in a range between -1 and 1__

We often see patterns or relationships in scatter plots. Pearson Correlation, which is a linear measure can be identified through a scatter plot by inspecting the "linearity of association" between two variables. 

If two variables have a correlation of +0.9,  this means the change in one item results in an almost similar change to another item. A correlation value of -0.9 means that the change is one variable results as an opposite change in the other variable. A pearson correlation near 0 would be no effect. 


Here are some example of pearson correlation calculations as scatter plots. 

![](correx.svg)

### Example: 

Imagine we have collected data for 12 days on daily Ice Cream Sales and average temperature on that day for a small icecream shop. We want to see if these two variables are associated with each other in any way. Here is the data:

```

Temp    Ice Cream 
°C      Sales

14.2°	$215
16.4°	$325
11.9°	$185
15.2°	$332
18.5°	$406
22.1°	$522
19.4°	$412
25.1°	$614
23.4°	$544
18.1°	$421
22.6°	$445
17.2°	$408
```
And here is the same data as a Scatter Plot:

<img src="scatt.svg" width=400>

We can easily see that hotter weather and higher sales go together. The relationship is good but not perfect.
The correlation for this example is 0.9575 which indicates a very strong positive relationship.

## Correlation is not Causation

A lot of times we have heard __“correlation is not causation”__ or __“correlation does not imply causation”__ . But what do we mean by saying this?

Causation takes a step further than correlation.
> Any change in the value of one variable will cause a change in the value of another variable, which means one variable makes other to happen. It is also referred as __cause and effect__.

Let's try to understand this with an example.


### Consider Hidden Factors

Suppose for the above ice cream sales example, we now have some extra data on number of homicide cases in New York. Out of curiosity,  we analyze sales numbers vs. homicide rate as scatter plot and see that these two also related to each other. Mind Blown .. Is Ice cream turning people into murderers ! 

<img src="ice1.png" width=400>

#### "Ice cream sales is correlated with number of homicides in New York" 

For our example, its actually the  weather as a hidden factor which is causing both these events. It is actually causing the rise in ice cream sales and homicides. As in summer people usually go out, enjoy nice sunny day and chill themselves with ice creams. So when it’s sunny, wide range of people are outside and there is a wider selection of victims for predators. There is no causal relationship between the ice cream and rate of homicide, sunny weather is bringing both the factors together. We can say that ice cream sales and homicide rate have a __causal relationship__ with weather.

This is reflected in the image below:

<img src="cc.png" width=300>

**Just after finding correlation, we shouldn't draw the conclusion too quickly. Instead we should take time to find other underlying factors as correlation is just the first step. Find the hidden factors, verify if they are correct and then conclude.**


Here is another (rather funny examples) of how correlation analysis may lead to inconceivable findings.


#### Number of Nicholas Cage movie releases correlates with people drowning in pools


<img src="cage.png" width=700>

So a casual relation above , or a cause-effect relationship - what do you think ?

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
