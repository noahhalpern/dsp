[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

Calculating all the requested values:

```python
>>> median = Median(sample)
>>> mean = Mean(sample)
>>> skewness = Skewness(sample)
>>> pearson_skewness = PearsonMedianSkewness(sample)
>>> print('Median: %f' % median)
>>> print('Mean: %f' % mean)
>>> print('Skewness: %f' % skewness)
>>> print('Pearson Skewness: %f' % pearson_skewness)
Median: 51226.454479
Mean: 74278.707531
Skewness: 4.949920
Pearson Skewness: 0.736126
```

We can use the `Prob()` function of `thinkstats2.Cdf` to compute the cumulative probability at a given value:
```python
>>> cdf.Prob(mean)
0.660005879566872
```

So 66% of households report a taxable income below the mean.

We can investigate the skew with an upper bound of 10 million by redefining `log_sample`:
```python
log_sample = InterpolateSample(income_df, log_upper=7.0)
```

This is what we come up with:
```Python
Median: 51226.454479
Mean: 124267.397222
Skewness: 11.603690
Pearson Skewness: 0.391565

>>> cdf.Prob(mean)
0.8565630665207663
```

With an upper bound of $10 million, over 85% of households report a taxable income below the mean.
