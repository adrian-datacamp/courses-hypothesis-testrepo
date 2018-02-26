---
title       : p-value and other statistics
description : Insert the chapter description here
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

---
## CHAPTER 1: 

## Exercise 1: The `flight_delays.csv` dataset contains US flight information, such as departure location, arrival location, cancellations, and delays for US airline companies. Select one of the airline companies (eg. United Airlines), and using a significance level of 0.01, determine whether this airline company experiences significantly different delays compared to overall average delays. 

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

`@hint`

`@instructions`


`@pre_exercise_code`
```{python}
import numpy as np
import pandas as pd
import scipy.stats as stats
import urllib.request

filename = 'https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/Chicago_violent_crimes.csv.gz.csv'
urllib.request.urlretrieve(filename, "Chicago_violent_crimes.csv.gz")

df = pd.read_csv('Chicago_violent_crimes.csv.gz')
#all_delays = df['DEPARTURE_DELAY'].dropna()

#print(df.head())

#df_ua = df.loc[df['AIRLINE'] == 'UA']
#ua_delays = df_ua['DEPARTURE_DELAY'].dropna()
```

`@sample_code`
```{python}
print(all_delays.mean())
print(ua_delays.mean())

# one sample t-test; compare population mean to one sample mean
popmean = all_delays.mean()
stats.ttest_1samp(ua_delays, popmean) 

```

`@solution`
```{python}
# leave blanc for now
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki
#  don't worry about it now

success_msg("Great work!")
```


---
## Exercise 2:

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

```
