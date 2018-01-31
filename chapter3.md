---
title       : Chapter 3
description : Insert the chapter description here



--- type:NormalExercise lang:python xp:100 skills:2 key:13e65f0ce8
## Exercise 1: 


*** =instructions

*** =hint

*** =pre_exercise_code
```{python}

def pdf_plotter(mean,std):
    range = np.arange(mean-4*std, mean+4*std, 0.001)
    plt.plot(range, stats.norm.pdf(range, mean, std))
    plt.xlim(mean-4*std, mean+4*std)
    
```

*** =sample_code
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

*** =solution
```{python}

```

*** =sct
```{python}

```