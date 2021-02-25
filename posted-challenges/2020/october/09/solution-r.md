---
layout: default
---

# solution in R

### create population and its wealth

First step was to import the required libraries. I used `tidyverse` as the core package and would be adding more packages along the way as needed.

```r
suppressPackageStartupMessages(library(tidyverse))
```

The challenge doesn't come with a dataset so I made one on my own under the name `pop` dataset. The characteristics of the population would include **gender**, **ethnicity**, **first_name**, **last_name** and **income**. To create the data for the first four columns, I used `randomNames` package and set some arbitary number for the random generator so that the code would be reproducible. Then, call the `randomNames()` to generate 2500 observations and save it to `pop` variable.

```r
suppressPackageStartupMessages(library(randomNames))
set.seed(42)
pop <- randomNames(2500, return.complete.data = T)
```

The **income** column would be randomly generated using `rnorm()` while keeping the specifications in mind; the population income is Normal distributed with mean of USD 50,000 and standard deviation of USD 12,500. I added the `income` column into `pop` dataset using `mutate()` where it'd be the very last column.

```r
pop <- pop %>% mutate(
  income = rnorm(2500, 50000, 12500))
```

When glancing at the `pop` dataset, notice that `gender` and `enthicity` column had been coded in numerics based on the [`randomNames` documentation's specification](https://cran.r-project.org/web/packages/randomNames/randomNames.pdf). For the purpose of later visualization, the numerics needed to be decoded into categorical variables as follows:

-`gender`
  - **0** = **Male**
  - **1** = **Female**
-`ethnicity`
  - **1** = **American Indian or Native Alaskan**
  - **2** = **Asian or Pacific Islander**
  - **3** = **Black (not Hispanic)**
  - **4** = **Hispanic**
  - **5** = **Black (not Hispanic)**
  - **6** = **Middle-Eastern, Arabic**


#### references

[randomNames()](https://cran.r-project.org/web/packages/randomNames/randomNames.pdf)
[value labels](https://www.statmethods.net/input/valuelabels.html)
