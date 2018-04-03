---
title: Template Chapter 1
description: This is a template chapter.
---
## Wiederholung wesentlicher Inhalte

```yaml
type: NormalExercise
lang: r
xp: 100
skills: 1
key: 641f650cf3
```

bla

`@instructions`
- bla

`@hint`
xxx

`@pre_exercise_code`
```{r}
library(dplyr)


```

`@sample_code`
```{r}
# alle benötigten Objekte sind bereits eingelesen
daten_auswahl1 <- ___

daten_auswahl2 <- ___

daten_auswahl3 <- ___

daten_auswahl4 <- ___

daten_auswahl5 <- ___
```

`@solution`
```{r}
daten_auswahl1 <- 1
```

`@sct`
```{r}
test_object("daten_auswahl1") 
test_error()
success_msg("Sehr gut!")
```
