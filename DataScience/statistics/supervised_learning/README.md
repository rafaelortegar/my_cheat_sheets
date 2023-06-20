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


# Applied Data Science
Supervised Learning: learning from labeled examples.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b970e081-d74c-4b9e-bb0a-4799f7bf0366)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d586c7c7-a8e4-4c1b-b44c-590ac7cf4007)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/cbe05731-922a-449d-bd2b-93868e5592ba)

## Regression:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/be2b6490-7c98-4ac0-a5ee-d0acb8376f37)

De difference between regression and classification is that when we want to predict a number or a float number, we want it to be regression. when we want to predict discrete variables, it is a classification problem.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/8b7351cd-cc2e-4d11-933f-c10e927734f5)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4cf99a07-56fa-4a17-8db3-e3b4eb1dcb1d)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b25c54fc-5760-4559-be6e-b6b0eaab7ce3)
because they are an idealization.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/e3fdd618-2732-4b8a-9fa4-18f6b4319486)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4ca9a2f4-b61b-4db4-aa98-a5b99af5f210)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/aed92958-c50a-4c96-995f-86c1f3d256e9)

* covariates: if one goes up, the other goes up as well.

### Linear Regression

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/e151005c-57f2-4f09-8650-002a8b195eac)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/796d2909-7e23-4011-b310-d4666eb74e2b)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/8c993e42-8eed-433d-96b0-68b8dcca564c)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/1807eb94-ea4d-4e31-b0a6-48c0fe870d4e)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/f59f7676-ff72-4765-bee0-361dd4aaf0e9)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/6367d429-9ecb-4ce7-a152-6186b683d4b1)

Empirical Risk Minimization: we have a true risk, which is a mathematical aproximation and we want predictor to keep empirical risk low.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/ee32f787-324f-405c-b7ed-1fcab49032d0)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4d70c492-195d-44fb-8e08-f1ba05f80034)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/7f300f04-c5be-45e5-b3fc-bf30121bdd60)

we get the residuals -> get their squared value of every prediction and sum. we want to minimize this error.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/5f3a7cbe-a0de-43af-87ab-e589dc97992c)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/987b57b0-4ead-41fe-ac40-10b09e86a656)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/216a7021-a835-4c09-9d36-f539ece31c1b)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/520b37d9-2ffe-44a8-a3f0-19e2711238e4)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/ddb31c01-0b01-48c5-8c07-77785f158c8d)
Maximum likelihood methodology: every observation has a probability to be seen. it chooses the data for theta that is more probable.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/2e65c0d1-4b4f-4f80-bbb6-b670eb497886)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/e0c8b5c9-edc0-4c58-a608-510febdc3ee0)


## Performance Assessment

### R squared:

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/a4de3852-6f82-4080-b1ac-3c2d0b185433)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/be039671-00f0-410c-8543-2e8716ff7f30)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/199bc11c-f9a4-4f25-b1e4-79fc9412d22a)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/8811bbef-f618-4421-8a9d-e1c850297ff8)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b87cd51a-05da-4d33-b517-8b0a86bf7e5a)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/235a0b7b-413c-41ba-ba9c-e84dab4d21b9)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d2097ae0-e7de-4717-8d08-5a739263c13f)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/3c05a233-37be-4da3-9f1f-d968535faae0)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/7955732f-0add-4d25-91d4-d8063dddbd88)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/67dec662-db24-40a8-9e8c-5cc7856be047)

### Mean squared error:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/5fa63eea-3f5b-4a1c-a3af-58708544437a)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/c7a0a729-f985-44a2-96ac-1f946dcbdd1c)
Linear regression is unbiased, so we focus on variance.
#### The distribution of the variance:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9ba7d243-206d-43eb-b97d-2538c6712897)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/103f72c9-b4ed-4881-a91c-ac2286c0e1f9)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/08825ba6-4bc6-421b-aec7-62de5e561716)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/bcff5430-8ddd-4391-95c1-1b02dbf70543)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/fec58c13-9c68-422b-adc7-d18509932642)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/931aabfc-37da-4ceb-84e8-15d044851c19)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d5c5fafa-6c41-4837-b5cf-2769ab95d72d)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/883d0de7-55d3-44a6-804c-16511a3ca5a9)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/fcaab198-c829-4755-8e02-5caec62b9d75)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/6e9b80bd-e9fc-4d64-ac82-afb362722ac2)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d8ed7b81-a71a-4d9c-ba65-d059297f05c2)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/6dff811e-97ea-469a-8064-8db1dfa46fea)
The random variable is the confidence interval.
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/cb10bf5e-3fb6-4cfd-b3ec-fd2d4ca9fa53)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/2b0bf9f7-2083-44ab-bc1d-ac211ab0d708)
of false discovery.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/57c395cf-1996-4dab-a4ad-c974365546e1)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/0c82c74c-632f-44c8-a7ab-ce793246c0f3)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/3d294a3c-75b1-4efe-ac9e-f2d6e0b92a76)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/11bf483a-220d-48b1-88fc-39ca6331ebac)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/f18b679f-9e2c-45c5-b831-c61536be812a)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/eab3ddf9-c7be-4619-9739-4dddd64e3a38)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/78b29c48-6e73-4f97-8d5c-b42b7fb10127)


## Making new predictions..

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/bab6ca58-6119-4ba3-bc21-51c343ecc10f)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/bd3b3ca1-bce7-4fee-b437-0fee233f32e2)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d968e1a9-27a1-433a-8c56-c8c32db99d09)
The confidence band is about the blue line

# Linear Model
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/7b6492a5-9474-4a1b-a7a2-99d043c91b3d)



## What can go wrong
- Multicollinearity
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/15664b94-690e-4711-8873-0efa16901664)
one way to remove variables is the PCA
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b334c99d-1250-4e67-9870-ffe2c164c83e)

algunas variables pueden estar correlacionadas. normalizing the variables is not going to solve the problem

the covariance matrix will be singular.


- Latent Variables

  A latent variable is a confounding variable.
  ![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4bae5fc6-d4a3-4c8d-9a06-f16d0837f69d)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/13c5119e-cfff-428b-ba10-69507ceaab1a)

Simpson paradox: ![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/5a8618a2-fe11-4164-a85a-a7a603951a05)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/1171c906-1ea1-4a99-a6d0-5262ab73d86f)

Mitigation of Latent variables:
- Add more variables
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9dfa46c1-ce1a-4541-ab46-49547936514c)
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/748e6bf6-8d9b-466c-a880-6b5185ed1dca)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/891d5c4f-3d2a-40f7-85e2-beb169124379)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/2960f9b1-4136-4f5d-9662-3099c7783bc2)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/a896b182-9147-4e28-936b-25f60b636fef)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/995dfc67-4fb6-4c51-b3c1-6ebdbfc55759)

- 
- 

## Using nonlinear features of the data
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/c5f6b4e9-eed0-4411-b042-0fe2ea94ad7d)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/c017a380-9db4-4f00-949a-93cea4df9a84)



## Overffitting and regularization
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/19a90cf9-b329-4125-ae72-3d49ab5bb132)



- Ridge Regression
  ![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/cfbd31bf-4635-4f41-bf6d-0782da781855)

- Sparse Regression and Lasso

  ![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4c9218f8-64bb-4afd-b00b-d4eda85b07c1)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9da4dac4-8d01-4f03-bd78-843e3fe729f6)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/771e588e-f66b-4c38-885e-5e6c8499c674)

In PCA you only look at the axis. Lasso looks axis and  Y´s
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/da25506d-2a3e-4180-9727-9f09a5bb5410)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4bf8984a-6eab-4179-983b-c0fb984eb431)


## Performance assessment, testing and validation
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/eced2e3b-2ef2-4a61-ba83-db82ebf6a2c5)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/60d65e62-891d-44c7-8e11-29be92101239)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/21eae3b6-4073-4c96-8e62-14ac7134335c)


- Training vs Testing
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b9d72ff8-8a14-4cfc-bd77-753e0050d5cd)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b8cd809b-aec1-4022-91ff-34136224c434)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/6c52d44e-cc9f-4d57-9aff-4c4cedfb99c8)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/7789dd25-505a-47e3-ae94-70ce044c7ca9)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/807814b7-6c3f-416b-8b8a-2d99f530b4db)


  
- Cross Validation
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/88a96bb6-e402-47db-87ec-ad9f7f655ae3)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/aa2c60a0-0010-4394-99d7-bdab8e065c1d)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/d4a85379-d11e-4422-bae9-6dcb9ef54bfc)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/f7198e45-6996-43ed-a405-c2547b1ec1be)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9f602adb-3706-4bee-9704-20266d6e9e0f)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/e44f2273-bd7a-4e09-bfcc-7dd27e9b0a28)

Performance on new data points can only be assessed on the test data set.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/35c4adf1-2880-4575-9aae-3316c1ca4acf)


![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/0834f627-df16-44b8-ae3c-d56e8c341caf)





- Bootstrap
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4818ef77-3cb7-4cd2-a727-0f88a0ddc002)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/af73b382-93ae-4c8b-b95f-fe2bf53807a6)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/33ed9213-168d-469d-b7ec-9d0c8f56dafc)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/320c49fe-94a1-45e1-b3f7-d2904b57a524)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/fb990b35-90bd-4c74-929b-50c7d098c69d)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/0f5c759f-9566-442a-9472-63b7acfddd04)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/aa1e36f1-86ea-4b36-a1ee-d0600c52c226)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/500e889a-17b0-4079-bd68-8b498b93248b)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/1202e7e7-092c-4e81-b276-cd3fe0e97a4c)


![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/352c648a-5e95-4f23-871a-150694472d64)
















