---
layout: default
---

# solution

First step was to import the required libraries. I used ```tidyverse``` as the core package and would be adding more packages along the way as needed.

```
suppressPackageStartupMessages(library(tidyverse))
```

Next step was to import the downloaded dataset.

```
dataset <- read_csv("archigos-mar-2016.csv")
```

There was an error with `borndate` variable for observation `#1417` which belonged to Didier Burkhalter but it was neglible.

The challenge describes a variable named `endyear` for the plot's x-axis which doesn't exist, so I did a little data manipulation to extract the `endyear`. I type-casted the `endyear` variable to _Date_ data type before using `substring()` to extract only the end year which then I added into the dataset.

```
dataset$endyear <- as.Date(dataset$endyear) # type-casting

dataset <- dataset %>% mutate(
  endyear = substring(enddate,1,4)
)
```

#### references

[substring()](http://rfunction.com/archives/1692)
