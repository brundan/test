---
title       : This is chapter 1
description : This is chapter 1 description
--- key:ff300667e9

## Interactive Exercise Title

```yaml
type: NormalExercise
lang: r
xp: 100
```

This basic exercise will challenge you to assign a variable in R.

`@instructions`
- Assign `5` to the variable `x` in the editor on the right.

`@hint`
Use `<-` for assignment.

`@pre_exercise_code`
```{r}
y <- 3
```

`@sample_code`
```{r}
# Assign 5 to the variable x
```

`@solution`
```{r}
# Assign 5 to the variable x
x <- 5
```

`@sct`
```{r}
test_error()
test_object("x",
            undefined_msg = "Make sure to define `x`!",
            incorrect_msg = "Have you correctly assigned 5 to `x`!")
success_msg("Awesome! It's considered good style to write spaces either side of the assignment arrow.")
```