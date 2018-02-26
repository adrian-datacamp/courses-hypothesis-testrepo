---
title       : Two sample hypothesis testing
description : Insert the chapter description here



--- 
## CHAPTER 3:


```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

`@hint`

`@instructions`
## Exercise 1: 

A survey of National Federation of Independence Business (NFIB) indicates that small businesses intended to increase their hiring as well as their capital expenditures during 2017 as compared with 2016. Suppose that, as part of a follow-up survey by NFIB, 20 small businesses, randomly chosen from the NFIB's list of 2,100 companies, show an average hiring from 2016 equal to 3.2 new employees per firm and a standard deviation of 1.5 hires. A random sample of 30 small businesses taken at the end of 2017 shows an average of 5.1 new hires and a standard deviation of 2.3 hires. At the alpha=0.01 level of significance, can you conclude that average hiring by all small businesses in 2017 increased as compared with 2016?


`@pre_exercise_code`
```{python}

def pdf_plotter(mean,std):
    range = np.arange(mean-4*std, mean+4*std, 0.001)
    plt.plot(range, stats.norm.pdf(range, mean, std))
    plt.xlim(mean-4*std, mean+4*std)
    
```

`@sample_code`
```{python}
import numpy as np
import pandas as pd
import scipy.stats as stats
import matplotlib.pyplot as plt

sb_2016 = np.random.normal(3.2, 1.5, 20)
sb_2017 = np.random.normal(5.1, 2.3, 30)

pop_2016 = np.random.normal(3.2, 1.5, 2100)
pop_2017 = np.random.normal(5.1, 2.3, 2100)

# plot the two distributions using the 'pdf_plotter' function

pdf_plotter(3.2, 1.5)
pdf_plotter(5.1, 2.3)

# test whether there is a difference between 2016 and 2017
stats.ttest_ind(pop_2016, pop_2017)

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


```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

*** =instructions

## Exercise 2: 

Recall the US flights dataset from Chapter 1. The conclusion was that the p-value is small enough to reject the null hypothesis that stated that there is no statistically significant difference between the mean of United Airlines delays and mean delays experienced overall. Using again the same data, evaluate whether there are less or more UA delays compared to overall US airline delays.


*** =hint

*** =pre_exercise_code
```{python}
import numpy as np
import pandas as pd
import scipy.stats as stats
import urllib.request

#filename = 'https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/flight_delays.csv.gz'
#urllib.request.urlretrieve(filename, "flight_delays.csv.gz")

#df = pd.read_csv('~/DataCamp/datasets/flight_delays.csv.gz')
#all_delays = df['DEPARTURE_DELAY'].dropna()

#df_ua = df.loc[df['AIRLINE'] == 'UA']
#ua_delays = df_ua['DEPARTURE_DELAY'].dropna()

```

*** =sample_code
```{python}
print('Test print!')   
```

*** =solution
```{python}
print(all_delays.mean())
print(ua_delays.mean())

# one sample t-test; compare population mean to one sample mean
popmean = all_delays.mean()
stats.ttest_1samp(ua_delays, popmean) 

# test direction of the effect (less or more delays) - one tailed hypothesis test

```

*** =sct
```{python}

```