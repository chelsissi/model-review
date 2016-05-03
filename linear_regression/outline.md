-----------------------------------------------------
Linear Regression (Yale)

Date: 2016-05-03

-----------------------------------------------------

Website:

http://www.stat.yale.edu/Courses/1997-98/101/linreg.htm

Linear Regression attempts to model the relationship between two variables by
fitting a linear equation to observe data. One variable is considered to be an
explanatory variable, and the other is considered to be a dependent variable.

For example, a modeler might want to relate the weights of individuals to their
heights using a linear regression model.

Before attempting to fit a linear model to observe data, a modeler should first 
determine whether or not there is a relationship between the variables of 
interest. This does not necessarily imply that one variable *cause* the other
(for example, higher SAT scores do not *cause* higher college grades), but that 
there is some significant association between the 2 variables. A **scatterplot**
can be a helpful tool in determining the strenth of the relationship between two 
variables. If there appears to be no association between the proposed explanatory
and dependent variable (i.e: the scatterplot does not indicate any increasing
or decreasing trends), then fitting a linear regression model to the data
probably will not provide a useful model. A valuable numerical measure of
association between two variables is the **correlation coefficient**, which is
a value between -1 and 1 indicating the strength of the association of the 
abserved data for the two variables.

A linear regression line has an equation of the form `Y = a + bX`, where `X` is
the explanatory variable and `Y` is the dependent variable. The slope of the 
line is `b`, and `a` is the intercept (the value of `y` when `x=0`).


1. Least-squares Regression.

	THe most common mothod for fitting a regression line is the method of least
	square. This method calculates the best-fitting line for the observed data 
	by minimizing the sum of squares of the vertical deviations from each data
	point to the line. (If a point lies on the fitted line exactly, then its
	vertical deviation is 0). Because the deviations are first squared, then
	summed, there are no cancellations between positive and negative values.

	Example:

	The dataset "Televisions, Physicians, and Lift Expectancy" contains, among 
	other variables, the number of people per television set and the number of
	people per physician for 40 countries. Since both variables probably reflect
	the level of wealth in each country, it is reasonable to assume that there
	is some positive association between them. After removing 8 countries with
	missing values from the dataset, the remaining 32 countries have a 
	correlation coefficient 0.852 for number of people per television set and
	number of people per physician. the R-square (`R^2`) value is 0.726 (the
	square of the correlation coefficient), indicating that 72.6% of the 
	variation in one variable may be explained by the other. 

	The regression equation is:

	```
	People.Phys. = 1019 + 56.2 People.Tel.
	```

	To view the fit of the model to the observed data, one may plot the computed
	regression line over the actual data points to evaluate the results. For
	this example, the plot appears to the right, with number of individuals per
	television set (the explanary variable) on the x-axis and number of
	individuals per physician per television (the dependent variable) on the 
	y-axis. While most of the data points are clustered towards the lower left
	corner of the plot (indicating relatively few individuals per television
	set and per physician), there are a few points which lie far away from the
	main cluster of the data. These points are known as **outliers**, and 
	depending on their location may have a major impact on the regression line.

2. Outlier and Influential Observations.

	










