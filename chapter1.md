---
title       : p-value and other statistics
description : Insert the chapter description here
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

---
## Plot the movies yourself

```yaml
type: NormalExercise
lang: python
xp: 100
skills: 1
key: 7942f6cb9a
```

background context on exercise

`@instructions`
- instruction 1
- instruction 2
- instruction 3

`@hint`


`@pre_exercise_code`
```{python}
import numpy as np
import pandas as pd
import scipy.stats as stats
df = pd.read_csv('https://s3.amazonaws.com/assets.datacamp.com/production/course_6777/datasets/Chicago_violent_crimes.csv.gz.csv')
# rename it back to .csv.gz
# unpack it using pandas
all_delays = df['DEPARTURE_DELAY'].dropna()

df_ua = df.loc[df['AIRLINE'] == 'UA']
ua_delays = df_ua['DEPARTURE_DELAY'].dropna()


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
# Get integer values for genres
_, ints = np.unique(movies.genre, return_inverse = True)

# Import matplotlib.pyplot
import matplotlib.pyplot as plt

# Make a scatter plot: runtime on  x-axis, rating on y-axis and set c to ints
plt.scatter(movies.runtime, movies.rating, c=ints)

# Show the plot
plt.show()
```

`@sct`
```{python}
# SCT written with pythonwhat: https://github.com/datacamp/pythonwhat/wiki

test_function("numpy.unique",
              not_called_msg = "Don't remove the call of `np.unique` to define `ints`.",
              incorrect_msg = "Don't change the call of `np.unique` to define `ints`.")

test_object("ints",
            undefined_msg = "Don't remove the definition of the predefined `ints` object.",
            incorrect_msg = "Don't change the definition of the predefined `ints` object.")

test_import("matplotlib.pyplot", same_as = True)

test_function("matplotlib.pyplot.scatter",
              incorrect_msg = "You didn't use `plt.scatter()` correctly, have another look at the instructions.")

test_function("matplotlib.pyplot.show")

success_msg("Great work!")
```
