---
title       : p-value and other statistics
description : Insert the chapter description here
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

---
## CHAPTER 1: Plot the movies yourself

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
```
import numpy as np
import pandas as pd
import scipy.stats as stats
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/Chicago_violent_crimes.csv.gz.csv')
# rename it back to .csv.gz
# unpack it using pandas
all_delays = df['DEPARTURE_DELAY'].dropna()

df_ua = df.loc[df['AIRLINE'] == 'UA']
ua_delays = df_ua['DEPARTURE_DELAY'].dropna()


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
## exercise 2

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
