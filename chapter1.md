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

--- type:NormalExercise lang:r xp:100 skills:1 key:617edb9d04
## This variation works OK

Changing `rownames()` to another vector of the correct length fixes things.

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
  geom_label(label = seq_len(nrow(cars)))
```

*** =solution
```{r}
# Draw a ggplot
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = seq_len(nrow(cars)))
```

*** =sct
```{r}
test_ggplot(1)
```

--- type:NormalExercise lang:r xp:100 skills:1 key:d2c512efab
## Is it an evaluation problem?

This variation creates the labels outside of the plot, but the problem remains.

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
labels <- rownames(cars)
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = labels)
```

*** =solution
```{r}
# Draw a ggplot
labels <- rownames(cars)
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = labels)
```

*** =sct
```{r}
test_ggplot(1)
```

--- type:NormalExercise lang:r xp:100 skills:1 key:285bb4993d
## Does it just not like strings?

The version that worked passed integers to the labels. Does it work with any integer labels?

Spoiler: no it doesn't.

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
  geom_label(label = sample(1:9, nrow(cars), replace = TRUE))
```

*** =solution
```{r}
# Draw a ggplot
ggplot(cars, aes(speed, dist)) + 
  geom_label(label = sample(1:9, nrow(cars), replace = TRUE))
```

*** =sct
```{r}
test_ggplot(1)
```