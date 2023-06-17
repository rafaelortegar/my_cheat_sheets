# Basic Terminologies

## Continuous and Categorical variables
A continuous variable can take an infinite number of distinct numerical values, possibly in a given range of numbers. For example, the Monthly Income of employees in a certain firm is a continuous variable. 

A categorical variable, on the other hand, can take only a limited (finite) number of distinct values. For example, in an image dataset of single handwritten digits, the digit in the image would be a categorical variable because it can only take a finite number of distinct values, in this case from 0 to 9, and nothing beyond that.

## Dependent and Independent Variables
In data science, given a set of variables, we need to establish the relationship between one variable and others. The variable to be estimated is dependent on the rest of the variables and hence called the dependent variable, while the remaining variables that affect the dependent variable are called independent variables.

For example, if we have 4 features Age, Education Level, Work Experience, and Salary, and need to find the relation between the Salary and the rest of the features, the Salary would be the dependent variable while Age, Education Level, and the Work Experience would be independent variables. 

## Variance and Standard Deviation
In statistics, it is important to understand the magnitude of the spread of the observed data from the Mean. 

Variance and Standard Deviation are two quantities that address this concept. To calculate the variance, we take the difference between each number in the dataset and the mean of the data, square this difference to make it positive (independent of sign), and finally divide the sum of the squares by the total number of values in the dataset.

Mathematically, the variance of the population can be given as follows: 

                                            $ Var= \frac{1}{n} \sum^n_{i=1}\left(x_i-\mu\right)^2$

Where LaTeX: x_i is a data point, LaTeX: \mu is the population mean, and LaTeX: n is the total number of data points. 

One of the major drawbacks of using variance, to understand the spread of the data, is its interpretability. The unit of variance is the square of the original unit of the data. To overcome this, another quantity is introduced, which is the square root of the variance. This is called the standard deviation of the population. 

Mathematically, the standard deviation of the population can be given as follows: 

                                      $ Sd=\sqrt{\frac{1}{n}\sum_{i=1}^n\left(x_i-\mu\right)^2}$

Being the square root of the variance, the standard deviation is more interpretable, having the same units as the original data points. The standard deviation is able to give a sense for the measure of spread of the dataset around its mean.

## Confidence Interval
Inferential statistics is associated with estimating the population parameters by extracting samples from the same population. In general, when we make an estimate about some quantity of the population (for example, mean), we come up with a single number. This single number is called a point estimate.  For example, if we take a sample from a population and the sample mean is 35, then our most reasonable estimate of the population mean is also 35. The drawback of point estimates is that we do not know how sure we can be that the population mean is close to 35. 
 
To increase the informativeness of our estimate, we associate it with another concept known as the confidence interval. 
A confidence interval is a range of values around the point estimate, constructed so that this range will contain the population parameter with a certain degree of confidence, expressed in percentage terms.

Let’s consider an example: Suppose we are extracting 100 samples (data sets) from a group of students in a university, where each sample has a certain number of records. We have calculated the mean age of students from each sample. When we construct confidence intervals (95% confidence level) using the method that will be covered in the first lecture, 95% of samples (data sets) are expected to result in confidence intervals that contain the true population mean.

The higher the confidence, the greater the width of the confidence interval.

# Supervised Learning: Regression
Let’s start with an example: Suppose you're given a dataset that contains the area of different houses and their market price. Your goal is to come up with an algorithm that will take the area of the house as its input and return its market price as the output.

In this example, the input variable, i.e., the area of the house is called the independent variable (X), the output variable, i.e., house price is called the dependent variable (Y), and this algorithm is an example of supervised learning. 

In supervised learning, algorithms are trained using the "labeled" data (in this example, the dependent variable - house price, is considered a label for each house), and after training the algorithm, we can predict the output for instances where this label (house price) is not known. "Labeled data" in this context simply means that the data is already tagged with the correct output. So, in the above example, we already know the correct market price for each house, and that data is used to teach the algorithm so that it can correctly predict the price of a house if it is not known beforehand.

The reason this paradigm of machine learning is known as supervised learning is that it is similar to the process of supervision that a teacher would conduct on the test results of a student on an examination, for example, the answers that the student gives (predictions) are evaluated against the correct answers (the labels), and the difference (error) is what the student would need to minimize to score perfectly on the exam. This is exactly how supervised machine learning algorithms learn.

There are mainly 2 types of supervised learning algorithms:

Regression, where the output variable is a continuous variable, for example, the price of a house.
Classification, where the output variable is categorical, for example, approve the loan or not, i.e., yes or no categories.
In this lecture, we will be learning about regression algorithms, which find great use in machine learning prediction of several numerical variables, such as price, income, age, time duration, etc.

Linear Regression
Linear Regression is useful for finding the linear relationship between the independent and dependent variables of a dataset. In the previous example, the independent variable was the area of the house and the dependent variable was the market price.

This relationship is given by the linear equation: LaTeX: Y\:=\:\theta^{\ast}_0+\theta^{\ast}_1X\:+W\:

Where LaTeX: \theta_0^{\ast} is the constant term in the equation, LaTeX: \theta_1^{\ast} is the coefficient of the variable LaTeX: X, and LaTeX: Wis the difference between the actual value LaTeX: Y and the predicted value (LaTeX: \theta_0^{\ast}+\theta_1^{\ast}X).

LaTeX: \theta_0^{\ast} and LaTeX: \theta_1^{\ast} are called the parameters of the linear equation, while LaTeX: X and LaTeX: Y are the independent and dependent variables, respectively.

What is an error?
With given LaTeX: X and LaTeX: Y in the training data, the aim is to estimate LaTeX: \theta_0^{\ast} and LaTeX: \theta_1^{\ast} in such a way that the given equation fits the training data the best. The difference between the actual value and the predicted value is called the error or residual. Mathematically, it can be given as follows:

                                 LaTeX: W\:=\:Y\:-\left(\theta_0^{\ast}+\theta_1^{\ast}X\right)

In order to estimate the best fit line, we need to estimate the values of LaTeX: \theta_0^{\ast} and LaTeX: \theta_1^{\ast}  which requires minimizing the mean squared error. To calculate the mean squared error, we add the square of each error term and divide the sum by the total number of records: 

                       LaTeX: Mean\:Squared\:Error\:=\:\frac{1}{n}\sum^n_{i=1}\left(Y-\theta_0^{\ast}-\theta_1^{\ast}X\right)^2

The equation of the best fit line can be given as follows: 

                                  LaTeX: Y'\:=\:\theta'_0\:+\:\theta'_1X

Where LaTeX: Y' is the predicted value, LaTeX: \theta'_0\:and\:\theta'_1 are the estimated parameters.

This equation is called the Linear Regression model. The above explanation is demonstrated in the below picture: 

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/956edc29-7130-4d27-ae01-025423f22856)


Before applying the model to the unseen data, i.e., the data not observed by the model during the training phase, it is important to check its performance to make it reliable. There are a few metrics to measure the performance of a regression model.

R-squared: R-squared is a useful performance metric to understand how well the regression model has fitted over the training data. For example, an R-squared of 80% reveals that the model is able to capture 80% of the variation in the dependent variable. A higher R-squared value indicates a better fit for the model.

Adjusted R-squared: The adjusted R-squared is a modified version of R-squared that takes into account the number of independent variables present in the model. The R-squared always increases when a new independent variable is added to the model, irrespective of whether that variable adds value to the model or not. Hence, R-squared might be misleading when we have multiple independent variables and cannot identify unnecessary variables included in the model.

However, when a new variable is added, the adjusted R-squared increases if that variable adds value to the model, and decreases if it does not. Hence, adjusted R-squared is a better choice of metric than R-squared to evaluate the quality of a regression model with multiple independent variables, because adjusted R-squared only remains high when all those independent variables are required to predict the value of the dependent variable well; it decreases if there are any independent variables which don't have a significant effect on the predicted variable.

RMSE: RMSE stands for Root Mean Squared Error. It is calculated as the square root of the mean of the squared 
 differences between the actual output and the predictions. The lower the RMSE the better the performance of the model. Mathematically, it can be given as follows:     
         LaTeX: Root\:Mean\:Squared\:Error\:=\:\sqrt{\frac{1}{n}\sum^n_{i=1}\left(Y_i-\theta^{\ast}_0-\theta^{\ast}_iX\right)^2}



