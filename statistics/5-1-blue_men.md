[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

**Problem**

*Exercise 5.1*
```
In the BRFSS (see Section 5.4), the distribution of heights is roughly normal with parameters μ = 178 cm
and σ = 7.7 cm for men, and μ = 163 cm and σ = 7.3 cm for women.
In order to join Blue Man Group, you have to be male between 5’10” and 6’1” (see http://bluemancasting.com). 

What percentage of the U.S. male population is in this range? Hint: use scipy.stats.norm.cdf.
```

**Code & Solution**
```
import scipy.stats

# Normal distribution of heights for men in the U.S.
mu = 178
sigma = 7.7

dist = scipy.stats.norm(loc=mu, scale=sigma)
cdf = dist.cdf

def inchestocm(inches):
    cm = inches*2.54
    return cm
    
minht = inchestocm(70)
print('5\'10" is', inchestocm(70), 'cm')
maxht = inchestocm(73)
print('6\'1" is', round(inchestocm(73),2), 'cm')

result = cdf(maxht)-cdf(minht)
print("The percentage of the population is", result)
# The percentage of the population eligible for the Blue Man Group is 0.342746837631
```
