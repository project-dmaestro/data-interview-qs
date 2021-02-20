---
layout: default
---

# solution in R

### create population and its wealth

First, import the required libraries. I'll be using `tidyverse` as the core package and I'll add more packages along the way as needed.

```r
suppressPackageStartupMessages(library(tidyverse))
```

The challenge doesn't come with a dataset so I'll make one on my own and will name it `pop` dataset. The characteristics of the population will include **gender**, **ethnicity**, **first_name**, **last_name** and **income**. To create the data for the first four columns, I'll use`randomNames` package and set some random arbitary number for the random generator so the code will be reproducible. Then, I'll call the `randomNames()` to generate 2500 observations and save it to `pop` variable.

```r
suppressPackageStartupMessages(library(randomNames))
set.seed(42)
pop <- randomNames(2500, return.complete.data = T)
```

The **income** column will be randomly generated using `rnorm()` while keeping the specifications in mind; the population income is Normal distributed with mean of USD 50,000 and standard deviation of USD 12,500. I added 



#### references

[randomNames()](https://cran.r-project.org/web/packages/randomNames/randomNames.pdf)
[value labels](https://www.statmethods.net/input/valuelabels.html)
