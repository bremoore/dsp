[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

# Exercise 2.4  
## Using the variable totalwgt_lb, investigate whether first babies are lighter or heavier than others. Compute Cohen’s d to quantify the difference between the groups. How does it compare to the difference in pregnancy length?

    diff = firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
    firsts_count, others_count = firsts.totalwgt_lb.count(), 
    others.totalwgt_lb.count()
    others_var, firsts_var = others.totalwgt_lb.var() , 
    firsts.totalwgt_lb.var()
    pooled_var = ((others_count * others_var) + (firsts_count * 
    firsts_var)) / (firsts_count + others_count)
    cohens_d = diff/math.sqrt(pooled_var)
    cohens_d


*-0.08867236333202932*

**The difference in means for both pregnancy length(PL) and totalwgt_lb(TW) is small. The difference between the two is that for PL cohen's d is posistive, but for TW it is negative. This suggests that for PL, the effect would cause the mean of the firsts to decrease and vice versa for TW.**