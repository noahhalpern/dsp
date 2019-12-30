[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

To determine how many people are between 5'10" and 6'1", we need to find the percentile rank of those two heights:
```python
>> short = dist.cdf(177.8) # 5'11" = 177.8cm
>> tall = dist.cdf(185.4) # 6'1" = 185.4cm
>> print(short, tall, tall-short)
0.48963902786483265 0.8317337108107857 0.3420946829459531
```

5'10" is the 49th percentile and 6'1" is the 83rd percentile. That means that 49% of men are shorter than 5'10", and 83% of men are shorter than 6'1".

The difference in percentiles is 34%, so 34% of men are between 5'10" and 6'1".

Running `df[df['htm3'].notnull() & df['sex']==1].info()` tells us that the survey recorded 154,407 male heights. This gives us a final result of
```python
>> np.round(154407*.34,0)
52498.0
```

So 52,498 people are between 5'10" and 6'1" (myself included!)
