[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

#### **Problem**
***Exercise 3.1*** *Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample. *

*Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household.*

*Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.*

*Plot the actual and biased distributions, and compute their means. As a starting place, you can use chap03ex.ipynb.*

#### **Answer & Explanation**
Actual PMF:
```
      0: 0.46617820227659301 
      1: 0.21405207379301322 
      2: 0.19625801386889966 
      3: 0.087138558157791451 
      4: 0.025644380478869556 
      5: 0.010728771424833181
```
Biased PMF:
```
      0: 0.0
      1: 0.20899335717935616
      2: 0.38323965252938175 
      3: 0.25523760858456823 
      4: 0.10015329586101177 
      5: 0.052376085845682166
 ```
Actual Mean:  1.02420515504

Biased Mean:  2.40367910066





#### Code

```
import thinkstats2
import nsfg
import thinkplot

resp = nsfg.ReadFemResp()
children = resp['numkdhh']

pmf = thinkstats2.Pmf(children, label='actual')
print(pmf)

def BiasedPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)
    
    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

biased_pmf = BiasedPmf(pmf,label='observed')
print(biased_pmf)

thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf,biased_pmf])
thinkplot.Show(xlabel='# children', ylabel='PMF')

actual_mean = pmf.Mean()
print("Actual Mean: ", actual_mean) # Actual Mean:  1.02420515504

biased_mean = biased_pmf.Mean()
print("Biased Mean: ", biased_mean) # Biased Mean:  2.40367910066
```
