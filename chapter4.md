---
title       : Multiple sample hypothesis testing
description : Insert the chapter description here


--- type:NormalExercise lang:python xp:100 skills:2 key:13e65f0ce8

## CHAPTER 4: Exercise 1

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

Analysis of variance has long been used in providing evidence of the effectiveness of pharmaceutical drugs. Such evidence is required before the FDA will allow a drug to be marketed. In a recent test of the effectiveness of a new sleeping pill, three groups of 25 patients each were given the following treatments. One group was given the drug, the second group was given a placebo, and the third group was given no treatment at all. The results are as follows. Drug group: 12, 17, 34, 11, 5, 42, 18, 27, 2, 37, 50, 32, 12, 27, 21, 10, 4, 33, 63, 22, 41, 19, 28, 29, 8. Placebo group: 44, 32, 28, 30, 22, 12, 3, 12, 42, 13, 27, 54, 56, 32, 37, 28, 22, 22, 24, 9, 20, 4, 13, 42, 67. No-treatment group: 32, 33, 21, 12, 15, 14, 55, 67, 72, 1, 44, 60, 36, 38, 49, 66, 89, 63, 23, 6, 9, 56, 58, 39, 59. Determine whether or not the drug is effective. What about the placebo? Give differences in average effectiveness, if any exist.



`@pre_exercise_code`
```{python}

import numpy as np
import pandas as pd
import scipy.stats as stats

drug = np.array([12, 17, 34, 11, 5, 42, 18, 27, 2, 37, 50, 32, 12, 27, 21, 10, 4, 33, 63, 22, 41, 19, 28, 29, 8])
placebo = np.array([44, 32, 28, 30, 22, 12, 3, 12, 42, 13, 27, 54, 56, 32, 37, 28, 22, 22, 24, 9, 20, 4, 13, 42, 67])
notreatment = np.array([32, 33, 21, 12, 15, 14, 55, 67, 72, 1, 44, 60, 36, 38, 49, 66, 89, 63, 23, 6, 9, 56, 58, 39, 59])

```

`@sample_code`
```{python}
n = notreatment.mean()
print(n)

```

`@solution`
```{python}
# leave blank for now
```

*** =sct
```{python}

```
---

## CHAPTER 4: Exercise 2

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 08a7ea7589
```

*** =instructions

*** =hint

*** =pre_exercise_code
```{python}

import numpy as np
import pandas as pd
import scipy.stats as stats
import urllib.request

filename = 'https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/Chicago_violent_crimes.csv.gz.csv'
urllib.request.urlretrieve(filename, "Chicago_violent_crimes.csv.gz")

df = pd.read_csv('Chicago_violent_crimes.csv.gz')

theft = df[df['Primary Category']=='THEFT']
assault = df[df['Primary Category']=='ASSAULT']
homicide = df[df['Primary Category']=='HOMICIDE']
burglary = df[df['Primary Category']=='BURGLARY']
arson = df[df['Primary Category']=='ARSON']

```

*** =sample_code
```{python}

```

*** =solution
```{python}

```

*** =sct
```{python}

```
