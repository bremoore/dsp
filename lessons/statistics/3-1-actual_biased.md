[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

# Exercise 3.1
## Something like the class size paradox appears if you survey children and ask how many children are in their family. Families with many children are more likely to appear in your sample, and families with no children have no chance to be in the sample. Use the NSFG respondent variable NUMKDHH to construct the actual distribution for the number of children under 18 in the household. Now compute the biased distribution we would see if we surveyed the children and asked them how many children under 18 (including themselves) are in their household.


    thinkplot.Pmf(thinkstats2.Pmf(resp['numkdhh']), label='actual')
    thinkplot.Show(xlabel='numkdhh', ylabel='PMF')

![pmf](pmf.png)

    thinkstats2.Pmf(resp['numkdhh']).Mean()

*1.024205155043831*

    biased_pmf = (thinkstats2.Pmf(resp['numkdhh'])).Copy()
    for x,p in biased_pmf.Items():
        biased_pmf.Mult(x,x)
    biased_pmf.Normalize()
    thinkplot.Pmf(thinkstats2.Pmf(biased_pmf, label='observed'))
    thinkplot.Show(xlabel='numkdhh', ylabel='PMF')

![biased_pmf](biased_pmf.png)
 
    thinkstats2.Pmf(biased_pmf).Mean()
*2.403679100664282*
