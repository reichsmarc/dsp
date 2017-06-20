[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

#### **Problem**
*Exercise 2.4 Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s d to quantify the difference between the groups. How does it compare to the difference in pregnancy length?*

#### **Explanation**
Cohen's D between first babies and others for the variable *weight* is approximately -0.089, which means that the first baby weighs very slightly less than later babies on average. For the variable for *length of pregnancy* Cohen's D is approximately 0.029.

The difference in means between first babies and other babies is small for both *weight* and *length of pregnancy*, but there is a slightly more meaningful difference with respect to *weight*.

#### Code

```
import thinkstats2
import nsfg
import math

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
 
firsts = live[live.birthord ==1]
others = live[live.birthord !=1]

first_wt = firsts.totalwgt_lb
others_wt = others.totalwgt_lb

first_len = firsts.prglngth
others_len = others.prglngth

def cohen_d(group1, group2):
    diff = group1.mean() - group2.mean()
    var1, var2 = group1.var(), group2.var()
    n1, n2 = len(group1), len(group2)

    d = diff / math.sqrt((n1*var1 + n2*var2)/(n1+n2))

    return d

wt_d = cohen_d(first_wt,others_wt)
print('Difference in Std. Dev. of Weight:' + wt_d)      # D = -0.088672927072602

len_d = cohen_d(first_len,others_len)
print('Difference in Std. Dev. of Length:' + len_d)     # D = 0.028879044654449883
```
