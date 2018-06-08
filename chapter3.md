---
title       : Two sample hypothesis testing
description : Insert the chapter description here



--- 
## CHAPTER 3: Exercise 1

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

`@hint`

`@instructions`

A survey of National Federation of Independence Business (NFIB) indicates that small businesses intended to increase their hiring as well as their capital expenditures during 2017 as compared with 2016. Suppose that, as part of a follow-up survey by NFIB, 20 small businesses, randomly chosen from the NFIB's list of 2,100 companies, show an average hiring from 2016 equal to 3.2 new employees per firm and a standard deviation of 1.5 hires. A random sample of 30 small businesses taken at the end of 2017 shows an average of 5.1 new hires and a standard deviation of 2.3 hires. At the $\alpha$ = 0.01 level of significance, can you conclude that average hiring by all small businesses in 2017 increased as compared with 2016?


`@pre_exercise_code`
```{python}

def pdf_plotter(mean,std,label):
    range = np.arange(mean-4*std, mean+4*std, 0.001)
    plt.plot(range, stats.norm.pdf(range, mean, std), label=label)
    plt.xlim(mean-4*std, mean+4*std)
    
import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt
    
```

`@sample_code`
```{python}
sb_2016 = np.random.normal(3.2, 1.5, 20)
sb_2017 = np.random.normal(5.1, 2.3, 30)

pop_2016 = np.random.normal(3.2, 1.5, 2100)
pop_2017 = np.random.normal(5.1, 2.3, 2100)

# plot the two distributions using the 'pdf_plotter' function

pdf_plotter(3.2, 1.5, 'sample')
pdf_plotter(5.1, 2.3, 'population')

plt.legend()
plt.show()

# test whether there is a difference between 2016 and 2017
st, p = stats.ttest_ind(pop_2016, pop_2017)

if (p > alpha):
    print('p-value > alpha, thus there is a statistically significant difference.')
else: 
    print('p-value <= alpha, thus there is no statistically significant difference.')


# test if there is an increase in 2017 (directional)
```

`@solution`
```{python}

```

`@sct`
```{python}

```


*** =sct
```{python}

```
---
## CHAPTER 3: Exercise 2

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: e94f3cb870
```

*** =instructions

Recall the US flights dataset from Chapter 1. The conclusion was that the p-value is small enough to reject the null hypothesis stating that there is no statistically significant difference between the mean of United Airlines delays and mean delays experienced overall. 

a) Using again the same data, evaluate whether there are less or more UA delays compared to overall US airline delays. The United Airlines flights have been preloaded in `df_ua` and delays in `ua_delays`. The information on all flights and all delays have been stored in `df_flights` and `all_delays`.

b) Compare the delays of two competing airline companies (Delta and United) and decide whether they are experiencing statisticall significant delays. If yes, in what direction. The Delta flights have been preloaded in `df_dl` and delays in `dl_delays`.


*** =hint

*** =pre_exercise_code
```{python}
import numpy as np
import pandas as pd
import scipy.stats as stats
import urllib.request

filename = 'https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/us_flight_delays.csv.gz.csv'
urllib.request.urlretrieve(filename, "us_flight_delays.csv.gz")

df_flights = pd.read_csv('us_flight_delays.csv.gz')
all_delays = df_flights['DEPARTURE_DELAY'].dropna()

df_ua = df_flights.loc[df_flights['AIRLINE'] == 'UA']
ua_delays = df_ua['DEPARTURE_DELAY'].dropna()

df_dl = df_flights.loc[df_flights['AIRLINE'] == 'DL']
dl_delays = df_dl['DEPARTURE_DELAY'].dropna()

```

*** =sample_code
```{python}

print(all_delays.mean())
print(ua_delays.mean())

# one sample t-test; compare population mean to one sample mean
popmean = all_delays.mean()
stats.ttest_1samp(ua_delays, popmean) 

# test direction of the effect (less or more delays) - one tailed hypothesis test

# compare two independent samples 
st, p = stats.ttest_ind(ua_delays, dl_delays) 

```

*** =solution
```{python}

```

*** =sct
```{python}

```





---
## CHAPTER 3: Exercise 3

The CEO of a company claims that 80 percent of his 1,000,000 customers are very satisfied with the service they receive. To test this claim, the Analytics team surveyed 100 customers, using simple random sampling. Among the sampled customers, 73 percent say they are very satisified. Based on these findings, can we reject the CEO's hypothesis that 80% of the customers are very satisfied? Use a 0.05 level of significance.

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 50d0e9a131
```

*** =instructions

*** =hint

*** =pre_exercise_code
```{python}
import numpy as np
import scipy.stats as stats
import math

# sample proportion
p = 0.73

# hypothesized proportion
P = 0.8

# sample size
n = 100

# population size
N = 1000000
```

*** =sample_code
```{python}
# calculate standard deviation
stddev = math.sqrt(P*(1-P)/n)

# calculate z-score as z = (p - P) / stddev
z_score = (p - P) / stddev

# since this is a two-tailed test, the p-value is the probability that the z-score is less than or greater than its +/- value
p_val = stats.norm.cdf(z_score)*2
```

*** =solution
```{python}

```

*** =sct
```{python}

```


--- type:MultipleChoiceExercise lang:python xp:50 skills:2 key:a939fe46dc
## CHAPTER 3: Exercise 4

Suppose the previous exercise is stated a bit differently. Suppose the CEO claims that at least 80 percent of the company's 1,000,000 customers are very satisfied. What needs to be changed in our hypothesis test to test this claim, given that all the other information remain unchanged (significance level, sample size, etc.)?

*** =instructions

- We use t-test for this question.
- We use again the z-test to perform a two-tailed test.
- We use again the z-test to perform a one-tailed test.
- Nothing, the result is the same.

*** =hint

*** =pre_exercise_code
```{python}

```

*** =sct
```{python}
test_mc(3)
```
