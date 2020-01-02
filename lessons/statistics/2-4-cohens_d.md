[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

A first order comparison can be done by looking at the two means:
```python
>>> firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()
(7.201094430437772, 7.325855614973262)
>>> firsts.totalwgt_lb.mean() - others.totalwgt_lb.mean()
-0.12476118453549034
```
It looks like first babies are slightly lighter than others

Cohen's d will give us more information about the difference in weights:
```python
>>> CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
-0.088672927072602
```
The Cohen's d tells us that first babies are lighter than others by 0.089 standard deviations.

We can check this:
```python
>>> live.totalwgt_lb.std()*-0.089
-0.12533811665564248
```
Standard deviation * Cohen's d ~ mean(firsts) - mean(others).
