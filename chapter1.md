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




`@pre_exercise_code`
```{python}
import numpy as np
import scipy.stats as stats
```

`@sample_code`
```{python}

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
## Testing Proportions

```yaml
type: PureMultipleChoiceExercise
key: b9a01998c7
xp: 50
skills: 2
```
Which question(s) cannot be answered using hypothesis testing for a proportion?

`@possible_answers`

- Do the complaints coming from Manhattan constitute more than 50% of the entire NYC complaints?
- Are there more than 50 percent of Americans who self-identify as liberal?
- Is the proportion of babies born male different from 50 percent?
- [Is the mean number of NYC complaints coming from Manhattan more than 100 per week?]


`@hint`

`@feedback`

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

Type I and Type II errors. `typeI_typeII_plotter()` function plots the NULL and alternative distributions, and highlights the Type I and Type II errors.

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

    plt.text(x=-1.2, y=0.15, s= "Null Hypothesis", fontsize=6)
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
