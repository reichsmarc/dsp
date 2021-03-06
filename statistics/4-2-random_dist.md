[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)
#### Problem:
*Exercise 4.2*
``` 
The numbers generated by random.random are supposed to be uniform between 0 and 1; that is, every value in the range should have the same probability.
Generate 1000 numbers from random.random and plot their PMF and CDF. Is the distribution uniform?
```
#### Answer/Explanation:
The random number generator in numpy does not generate a uniform distribution of numbers between 0 and 1. This can be seen in the two plots in the below code. In the PMF plot, the distribution between numbers is not uniform (shown by thicker 'bands' of values). This effect is clearer in the CDF plot, where we would expect a perfectly smooth line from the origin to the (1,1) point if the selection were perfectly uniform.

#### Code:
```
import thinkstats2
import numpy as np
import thinkplot

randnum = np.random.random(1000)

pmf = thinkstats2.Pmf(randnum, label = 'random')

# Plotting PMF as step function
width = 0.4/16
thinkplot.PrePlot(1)
thinkplot.Pmf(pmf, linewidth=0.05)
thinkplot.Show(xlabel='Value', ylabel = 'PMF')

cdf = thinkstats2.Cdf(randnum, label = 'random')

thinkplot.Cdf(cdf)
thinkplot.Show(xlabel = 'Value', ylabel='CDF')
```
