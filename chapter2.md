---
title       : Problems with faceting
description : Insert the chapter description here
--- type:NormalExercise lang:r xp:100 skills:1 key:186d5d64ff
## Any facet works?

Calling `test_ggplot()` on a plot with the wrong facet formula causes the SCT to incorrectly succeed.

*** =instructions

- Run the code to draw a ggplot.

*** =hint

*** =pre_exercise_code
```{r}
library(ggplot2)
```

*** =sample_code
```{r}
# The facet formula is different in the solution
ggplot(CO2, aes(conc, uptake)) +
  geom_point() +
  facet_grid(Treatment ~ Type)

```

*** =solution
```{r}
# The facet formula is different in the solution
ggplot(CO2, aes(conc, uptake)) +
  geom_point() +
  facet_grid(. ~ Plant)
  
```

*** =sct
```{r}
test_ggplot()
```


--- type:NormalExercise lang:r xp:100 skills:1 key:b3e4c4deaa
## Does the same issue occur with facet_wrap()

Calling `test_ggplot()` on a plot with the wrong facet formula causes the SCT to incorrectly succeed.

*** =instructions

- Run the code to draw a ggplot.

*** =hint

*** =pre_exercise_code
```{r}
library(ggplot2)
```

*** =sample_code
```{r}
# The facet formula is different in the solution
ggplot(CO2, aes(conc, uptake)) +
  geom_point() +
  facet_wrap(~ Type)

```

*** =solution
```{r}
# The facet formula is different in the solution
ggplot(CO2, aes(conc, uptake)) +
  geom_point() +
  facet_wrap(~ Plant)
  
```

*** =sct
```{r}
test_ggplot()
```
