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
