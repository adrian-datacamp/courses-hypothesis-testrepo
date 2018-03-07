---
title       : p-value and other statistics
description : Insert the chapter description here
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

---
## CHAPTER 1: Exercise 1 


```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

`@hint`

`@instructions`

The `us_flight_delays.csv` dataset contains US flight information, such as departure location, arrival location, cancellations, and delays of US airline companies. Select one of the airline companies (e.g. United Airlines), and using a significance level of $\alpha$ = 0.01, determine whether this airline company experiences significantly different delays compared to overall average delays. 

Based on your obtained p-value, the following can be inferred about United Airlines:

a) UA experiences significantly different delays

b) there is no statistically significant difference between UA delays and overall all airline company delays

c) UA experiences on average more delays 

d) UA experiences on average less delays


`@pre_exercise_code`
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

# preloaded \alpha value
alpha = 0.01
```

`@sample_code`
```{python}
print(all_delays.mean())
print(ua_delays.mean())

# one sample t-test; compare population mean to one sample mean
popmean = all_delays.mean()
st, p = stats.ttest_1samp(ua_delays, popmean)

# use the obtained p-value and given significance level to assess whether you should reject or fail to reject the hypothesis
if (p > alpha):
    print('p-value > alpha, thus we fail to reject the NULL hypothesis.')
else: 
    print('p-value <= alpha, thus we reject the NULL hypothesis.')
```

`@solution`
```{python}
# leave blank for now
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

success_msg("Great work!")
```


---
## CHAPTER 1: Exercise 2

```yaml
type: NormalExercise
key: 1b8445f214
lang: python
xp: 100
skills: 2
```


`@instructions`

Type I and Type II errors. `typeI_typeII_plotter()` function plots the NULL hypothesis and alternative distributions and highlights the Type I and Type II errors.

`@hint`

`@pre_exercise_code`
```{python}

import numpy as np
from scipy.stats import norm
import matplotlib.pyplot as plt

def typeI_typeII_plotter():
    plt.figure(figsize=(12,10))
    range = np.arange(-4, 4, 0.001)
    plt.plot(range, norm.pdf(range, 0, 1))
    range = np.arange(-4, 10, 0.001)
    plt.plot(range, norm.pdf(range, 3, 2))

    plt.fill_between(x=np.arange(-4,-2,0.01), y1= norm.pdf(np.arange(-4,-2,0.01)), facecolor='red', alpha=0.35)
    plt.fill_between(x=np.arange(-2,2,0.01), y1= norm.pdf(np.arange(-2,2,0.01)), facecolor='white', alpha=0.35)
    plt.fill_between(x=np.arange(2,4,0.01), y1= norm.pdf(np.arange(2,4,0.01)), facecolor='red', alpha=0.5)

    plt.fill_between(x=np.arange(-4,-2,0.01), y1= norm.pdf(np.arange(-4,-2,0.01),loc=3, scale=2), facecolor='white', alpha=0.35)
    plt.fill_between(x=np.arange(-2,2,0.01), y1= norm.pdf(np.arange(-2,2,0.01),loc=3, scale=2),facecolor='blue', alpha=0.35)
    plt.fill_between(x=np.arange(2,10,0.01), y1= norm.pdf(np.arange(2,10,0.01),loc=3, scale=2), facecolor='white', alpha=0.35)

    plt.text(x=-1.8, y=0.15, s= "Null Hypothesis", fontsize=6)
    plt.text(x=2.5, y=0.13, s= "Alternative", fontsize=6)
    plt.text(x=2.1, y=0.01, s= "Type 1 Error", fontsize=6)
    plt.text(x=-3.2, y=0.01, s= "Type 1 Error", fontsize=6)
    plt.text(x=0, y=0.02, s= "Type 2 Error", fontsize=6)
    
    plt.show()
```

`@sample_code`
```{python}
typeI_typeII_plotter()
```

`@solution`
```{python}

```

`@sct`
```{python}

success_msg("Great work!")
```
