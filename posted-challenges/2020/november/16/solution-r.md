---
layout: default
---

First step was to import the required libraries. I used `tidyverse` as the core package and would be adding more packages along the way as needed.

```r
suppressPackageStartupMessages(library(tidyverse))
```

Next step was to import the dataset. The `Gender` column had to be type-casted into *character* during import. The column had been read as *logical* due to the **F** by default stands for **FALSE** instead of **Female**. Thus, the `read.csv()` threw an error once **M** was read in because it was expecting **T** for **TRUE**, not **M** for **Male**. 

```r
dataset <-
  read.csv(
    "https://raw.githubusercontent.com/guipsamora/pandas_exercises/master/06_Stats/US_Baby_Names/US_Baby_Names_right.csv",
    colClasses = c("Gender" = "character")
  ) %>%
  select(-X)
```

# solution in R

[back](./challenge.md)
