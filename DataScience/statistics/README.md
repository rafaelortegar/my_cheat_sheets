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

6. 
