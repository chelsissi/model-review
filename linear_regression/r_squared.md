-----------------------------------------------------
R-Squared

Date: 2016-05-03

-----------------------------------------------------

Website:

```
http://blog.minitab.com/blog/adventures-in-statistics/regression-analysis-how-do-i-interpret-r-squared-and-assess-the-goodness-of-fit
```

After you have fit a linear model using regression analysis, ANOVA, or design
of experiments (DOE), you need to determine how well the model fits the data.
This is a goodness-of-fit statistics. We will explore the R-squared (`R^2`) 
statistic, some of its limitation, and uncover some surprses along the way. For 
instance, low R-squared values are not always bad and high R-squared values are
not always good!

1. What is Goodness-of-Fit for linear model?

	Linear regression calculates an equation that minimizes the distance between
	the fitted line and all of the data points. Technically, orginary least
	square (OLS) regression minimizes the sum of the squared residuals.

	In general, a model fits the data well if the difference between the 
	observed values and the model's predicted values are small and unbiased.

	Before you look at the statistical masures for goodness-of-fit, you should
	check the residual plots Residual plots can reveal unwanted residual 
	patterns that indicate biased results more effectively than numbers. When
	your residual plots pass muster, you can trust your numerical results and
	check the goodness-of-fit statistics.

2. What is R-squared?

	R-squared is a statistical measure of how close the data are to the fitted 
	regression line. It is also known as the coefficient of determination, or 
	the coefficient of multiple determination for multiple regression.

	The definition of R-squared is fairly straight-forward; it is the percentage
	of the response variable variation that is explained by a linear model, or:

	R-squared: Explained variation / Total variation

	R-squared is always between 0 and 100%.
		
		- 0% indicates that the model explains non of the variability of the
		response data around its mean.

		- 100% indicated that the model explains all the variability of the 	
		response data around its mean.

	In general, the higher the R-squared is, the better the model fits your data,
	However, there are important conditions for this guideline that I'll talk
	about later.

3. Graphical Representation of R-squared.

	Plotting fitted values by observed values graphically illustrates different
	R-squared values for regression models.

	http://cdn2.content.compendiumblog.com/uploads/user/458939f4-fe08-4dbc-b271-efca0f5a2682/742d7708-efd3-492c-abff-6044d78e3bbd/Image/f2ebe39707aad6c7787d988ae833cdfb/fittedxobserved.gif	

	The regression model on the left accounts for 38.0& of the variance while
	the one on the right accounts for 87.4%. The more variance that is accounted 
	forby the regression model, the closer the data points will fall to the 
	fitted regression line.	Theoretically, if a model could explain 100% of the 
	variance, the fitted values would always equal the observed values and, 
	therefore, all the data points would fall on the fitted regression.

4. Key Limitation of R-squared

	R-squared **cannot** determine whether the coefficient estimates and 
	predictions are biased, which is why you must assess the residual plots.

	R-squared does not indicate whether a regression model is adequate. You can
	have a low R-squared value for a good model, or high R-squared value for a 
	model that does not fit the data!

	**Future Reading**

	```
	http://blog.minitab.com/blog/adventures-in-statistics/r-squared-shrinkage-and-power-and-sample-size-guidelines-for-regression-analysis
	```

5. Are load R-squared values inherently bad?

	**No!** There are two major reasons why it can be just fine to have low
	R-squared values.

		- In some fields, it is entirely expected that your R-squared values
		will be low. For example, any field that attempts to predict human 
		behavior, such as psychology, typically has R-squared values lower than
		50%. Humans are simply harder to predict than, say, physical processes.

		- Furthermore, if your R-squared value is low but you have statistically
		significant predictors, you can still draw important conclusions about 
		how changes in the predictor values are associated with changes in the 
		response value. Regardless of the R-squared, the significant coefficient
		still represent the mean change in the response for one unit of change 
		in the predictor while holding other predictors in the model constant.
		Obviously, this type of information can be extremely valuable.

		Future reading reference:

		```
		http://blog.minitab.com/blog/adventures-in-statistics/how-to-interpret-a-regression-model-with-low-r-squared-and-low-p-values
		```

		A low R-squared is most problematic when you want to produce predictions
		that are reasonably precise (have a small enough predictional interval).
		How high should the R-squared be for prediction? Well, that depends on 
		your requirements for the width of a prediction interval and how much 
		variability is present in your data. While a high R-squared is required
		for precise predictions, it's not sufficient by itself, as we shall see.

6. Are High R-squared values inherently Good?

	**NO!** A high R-squared does not necessarily indicate that the model has a
	good fit. That might be a surprise, but look at the fitted line plot and 
	residual plot below. The fitted line plot displays the relationship between
	semiconductor electron mobility and the natural log of the density for real
	experimental data.

	`<example plot>`

	The fitted line plot shows that these data follow a nice tight function and
	R-square is 98.5%, which sounds great. However, look closer to see how the
	regression line systematically over and under-predicts the data (bias) at
	different points along the curve. You can also see patterns in the Residuals
	versus fitted plot, rather than the randomness than you want to see. This
	indicates a bad fit, and serves as a reminder as to why you should always
	check the residual plot.

	The example comes from my post about choosing between linear and nonlinear
	regression:

	```
	http://blog.minitab.com/blog/adventures-in-statistics/linear-or-nonlinear-regression-that-is-the-question
	```

	In this case, the answer is to use non-linear regression because linear
	model are unable to fit the specific curve that these data follow.

	However, similar biases can occur when you linear model is missing important
	predictors, polynomial terms, and interaction terms. Statisticians call this 
	specification bias, and it is caused by an underspecified model. For this 
	type of bias, you can fix the residuals by adding the proper terms to the 
	model.

	For more information about how a high R-squared is not always good thing:

	```
	http://blog.minitab.com/blog/adventures-in-statistics/five-reasons-why-your-r-squared-can-be-too-high
	```

7. Closing thoughts on R-squared.

	R-squared is a handy, seemingly intuitive measure of how well your linear
	model fits a set of observations. However, as we saw, R-squared doesn't tell
	us the entire story. You should evaluate R-squared values in conjunction
	with residual plots, other model statistics, and subject area knowledge in
	order to round out the picture (pardon the pun).

	While R-squared provides an estimate of the strength of the relationship 
	between your model and the response variable, it does not provide a formal 
	hypothesis test for this relationship. The **F-test of overall significance**
	determines whether this relationship is statistically significant.

	Next: adjusted R-squared and predicted R-squared. These two measures overcome
	specific problems in order to provide additional information by which you 
	can evaluate your regression model's explanatory power.

