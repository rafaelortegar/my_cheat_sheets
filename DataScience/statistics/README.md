- $A \cup B$
- $A \cap B$
- $$ P($A \cup B$) $$
- P($A \cup B$) = P(A) + P(B) - P($A \bigcap B$)
P($A \bigcap B$) = P(A)*P($B|A$)

  
P($B|A$) = $\frac{A \bigcap B}{P(A)}$
# Inter Quartile Range

$$Inter Quartile Range = Q_3 - Q_1$$

# Sample

$$ variance = \frac{1}{(n-1)} * \sum\limits _{i=1} ^{n}{( x_i - \bar{x})}^{2} $$ 

$$ standard deviation = \sqrt{ \frac{1}{(n-1)} * \sum\limits _{i=1} ^{n}{( x_i - \bar{x})}^{2} }$$ 

$$ Coefficient of Variation = \frac{S}{(\bar{x})} $$
# Population

$$ variance = \frac{1}{(N)} * \sum\limits _{i=1} ^{n}{( x_i - \mu)}^{2} $$ 

$$ standard deviation = \sqrt{ \frac{1}{(N)} * \sum\limits _{i=1} ^{n}{( x_i - \mu)}^{2} }$$ 

$$ Coefficient of Variation = \frac{\sigma}{\mu} $$

# The empirical rule
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/ed88989c-0746-4f3e-819b-9bc26ce5a87b)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/5a35e47e-55a1-4b49-aa9d-86971e2713a9)

# Chebishev rule
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/85727d26-3f5e-4828-bec2-ef0bd793a6c9)

for when data is not bel shaped

# Distributions

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/3ad8ca6b-170c-4024-b54b-c1683cc85656)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/fc6f2da0-91ae-4148-b7b0-8809113459ca)


In a boxplot, the outliers are calculated as those outside the range of 1.5*IQR from the quartiles

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/df29a503-f9bc-4d9d-a2a5-accdd6945337)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/90081b9a-5576-45fe-947d-0ab48aee945e)

# Correlation Analysis

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/e5440ff8-39cc-432d-8b73-78e3fb035a4f)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/06207104-25a4-4bb7-8ab8-46a4385780e1)

This correlation coefficioent removes the units.

# Probability

$$ probability =  \frac{number of ocurrences of the event}{number total of events} $$

## Rules for computing probability
1. Addition Rule - Mutually Exclusive Events
P($A \cup B$) = P(A) + P(B)

2. Addition Rule - Events are not Mutually Exclusive
P($A \cup B$) = P(A) + P(B) - P($A \bigcap B$)

3. Multiplication Rule - Independent Events
P($A \bigcap B$) = P(A)*P(B)

4. Multiplication Rule - Events are not independent
P($A \bigcap B$) = P(A)*P($B|A$)

So, if they are independent:
P($B|A$) = P(B)

5. Conditional Probability:
P($B|A$) = $\frac{A \bigcap B}{P(A)}$

# Distributions
## Binomial - Bernoulli

## Uniform distribution
All the outcomes have equal probability of ocurrence and are mutually exclusive.
Useful when we are interested in unbiased selection.

* Discrete Unifrom Distribution: Can take a finite number (m) of values and each value has equal probability of selection.
* Continuous Uniform Distribution: Can take any value between a specified range.

```python
import scipy.stats as stats

# time taken to fix bugs
# get distribution:
x = np.linspace(1,5,50)
probs = uniform.pdf(x,loc=1, scale=4)

# Find the probability that a randomly selected software debugging requires a max of 3 hours
CDF: Of a random variable(x) is the probability that X will take the value less than or equal to x. It can be represented mathematically as below:

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9bc3975a-5335-4e50-a4de-f0783b6d113c)

In our case, random variavle(x) is the number of hours.
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/883cf619-7a61-4c02-ae87-90122d253012)
uniform.cdf(x=3,loc=1,scale=4)

# Find the probability that it requires more than 2 hours:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/46d996c1-4473-4792-a982-c0c30e0b0e90)

1-uniform.cdf(x=2,loc=1,scale=4)

# 50th percentile of software debugging time:
uniform.ppf(q=0.5, loc=1, scale=4



```
## Normal distribution
mean: 0
standard deviation = 1

is symmetric
total area under the curve is 1
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/88043601-dfb4-4e76-9117-6c9aa6a20bf0)

process of standardization:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/322b2c24-969d-45b6-8c18-bb72a6a6f3d4)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/bc7c953f-eabc-47ed-9e21-9e5e70ede79c)
Area to the left of a distribution: cumulative distribution function
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/45c7f0a5-739d-4676-a930-1d746136c12f)

```python
prob_less_than_800 = norm.cdf(800,mu,sigma)
```
 * calculate the probability that a student will have more than 1300:
```python
prob_greater_than_1300 = 1-norm.cdf(1300,mu,sigma)
```

* calculate the minimum markas a student must score in order to be in the 90th percentile:
```python
score_90th_percentile = norm.ppf(0.90,mu,sigma)
```

# Sampling distributions

In the real world, it is not always possible to get an exact idea about the parameters of the population. This is why it becomes important to take samples from the population. The idea behind inferential statistics is to approximate the population parameters by taking samples from it. Hence, a good sample is one that represents the population well.

The mean of the sampling distribution of $\bar{x}% is $\mu$ and the standard deviation of the sampling distribution of $\bar{x}$ is $\sigma/\sqrt{n}$.


If n (>30) samples are drawn from a population that has a mean μ and a standard deviation σ. The sampling distribution will follow a normal distribution with:
Mean: μ; Standard Deviation: σ / √n

# Estimation:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/9b73beac-181b-4168-85c0-caee06e64241)

* Point estimation:

Is a single value of a statistic.
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/7d86ef1b-6774-465c-8cfc-9efd6572e20c)


* Interval Estimation:
Provides an interval, or a range of values, which is expected to cover the true unknown parameter.

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/418954d7-d769-4bb9-a007-37ae9d8ae96e)

The upper and lower limits of the interval are determined using the distribution  of the sample mean and a multiplier, which specifies the "confidence".

The confidence interval has the following interpretation:
The interpretation of a 95% confidence interval is that, if the process is repeated a large number of times, then the intervals so constructed, will contain the true population parameter 95% of times.

A 100% confidence interval will include all possible values. Hence, there will not be any insight to the problem.

# Hypothesis testing
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/1ace5058-e9eb-4519-afb8-7c6ac2060b7d)

Often we are interested in a population parameter
a hypothesis is a conjecture about a population parameter
The objective of the hypothesis testing is to SET a value for the parameters and perform statistical TEST to see whether that value is tenable in the light of the evidence gathered from the sample.

## Stating the hypothesis
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/b48657e9-0cc2-442e-87ca-5797b6a7fe1a)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/4baf5451-2484-44cd-8fed-7060d6325f7f)

## Type of errors:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/159aaa0e-5c75-4ca4-aac7-87da5c910e94)

## Hypothesis testing template
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/a402c79b-c563-4dd9-806d-f4113928fff7)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/5b7cb502-50bc-4842-9753-8573c696632e)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/decf9b35-9903-4a69-a2db-bb9bd84a5f66)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/a63f39d1-bbe0-40f8-9479-0177f1385632)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/c2b0aa22-5fe4-4827-8650-fadd5e5e74c5)


## One tailed vs two tailed tests
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/bdd51b4b-56c6-4490-8bdd-7fdb44ae9406)

![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/64f43997-534f-4670-95db-34d484944807)


## Hypothesis testing FAQS
1. How to set the value of k for binom.pmf() and binom.cdf() functions?

Tags: #pmf #cdf #probability

If we want to calculate the probability that the random variable X is exactly equal to x, then binom.pmf(k=x,...) will be used.

If we want to calculate the probability that the random variable X is less than or equal to x, then binom.cdf(k=x,...) will be used.

If we want to calculate the probability that the random variable X is greater than or equal to x, then 1-binom.cdf(k=x-1,...) will be used.

 

2. What are the Empirical rules of a normal distribution?

Tags: #normal distribution #standard deviations #empirical rule

The empirical rule states that 68% of the observations of a normal distribution fall within the first standard deviation from the mean (µ ± σ), 95% within the first two standard deviations from the mean (µ ± 2σ), and 99.7% within the first three standard deviations from the mean (µ ± 3σ).

Let’s assume pizza delivery timings in a restaurant are known to be normally distributed.

µ(mean delivery time): 30 minutes

σ(standard deviation) : 5 minutes

Using the Empirical Rule, we can determine that,

68% of the delivery times are between 25-35 minutes (30 ± 5)

95% of the delivery times are between 20-40 minutes (30 ± 2x5)

99.7% of the delivery times are between 15-45 minutes (30 ±3x5)

 

3. What is the degree of freedom?

Tags: #estimate #observations

The Degree of freedom of an estimate is the number of independent pieces of information that went into calculating the estimate. Let's understand with an example. Suppose there are 10 observations, and we have an estimate of the sum of those 10 observations. Now, if 9 of the ten observations are known to us, the 10th one can be calculated by subtracting the sum of 9 observations from the estimate of the sum of all observations. This way, if 9 of the observations are known to us, then the one left out observation is redundant. So, we say that the degrees of freedom for the estimate of the sum is 10 - 1 = 9.

This applies universally to all other estimates as well. So, in general terminology for n observations, the degree of freedom for an estimate of these n observations is k = n-1.

 

4. What are the functions used in Statistical Analysis from the Scipy Stats library to calculate probabilities in a normal distribution?

Tags: #pdf #cdf #ppf

pdf(x, loc=0, scale=1) - Probability density function.

cdf(x, loc=0, scale=1) - Cumulative distribution function.

ppf(q, loc=0, scale=1) - Percent point function (inverse of cdf - percentiles).



# Protection levels on hypothesis testing:
![image](https://github.com/rafaelortegar/my_cheat_sheets/assets/51694410/abc500b8-5d58-4e70-808b-96cd8bb03b7b)
$FDR<=10%$


$FWER<=5%$
we want to control the probability that 