[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

firsts_b = (live[live.birthord == 1]).totalwgt_lb
others_b = (live[live.birthord !=1 ]).totalwgt_lb

def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d

CohenEffectSize(firsts_b, others_b)

The computed Cohen Effect Size of first born babies and others is the absolute value of -0.089. This is smaller than what is needed to be considered a "small effect size" (0.2), so that means the difference between the two sample population groups is negligible.  
