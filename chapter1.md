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

The `us_flight_delays.csv` dataset contains US flight information, such as departure location, arrival location, cancellations, and delays for US airline companies. Select one of the airline companies (e.g. United Airlines), and using a significance level of $\alpha$ = 0.01, determine whether this airline company experiences significantly different delays compared to overall average delays. 


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

`@hint`

`@pre_exercise_code`
```{python}

```

`@sample_code`
```{python}

```

`@solution`
```{python}

```

`@sct`
```{python}

success_msg("Great work!")
```
