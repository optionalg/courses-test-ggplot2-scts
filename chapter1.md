---
title       : Testing test_ggplot() 
description : A problem with testwhat?

--- type:NormalExercise lang:r xp:100 skills:1 key:64cc318888
## Demoing a failing SCT

Calling `test_ggplot()` on a plot with `geom_label(label = rownames(data))` causes the SCT to incorrectly fail.

*** =instructions

- Run the code to draw a ggplot.

*** =hint

*** =pre_exercise_code
```{r}
library(ggplot2)
```

*** =sample_code
```{r}
# Draw a ggplot
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = rownames(cars))
```

*** =solution
```{r}
# Draw a ggplot
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = rownames(cars))
```

*** =sct
```{r}
test_ggplot(1)
```
