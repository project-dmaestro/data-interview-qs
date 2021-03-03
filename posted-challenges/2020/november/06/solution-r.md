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

There was an error with `borndate` for observation `#1417` which belonged to Didier Burkhalter but it was neglible. The challenge describes a variable named `endyear` for the plot's x-axis which doesn't exist. Thus, I did a little data manipulation to extract the `endyear`.

#### references

[substring()](http://rfunction.com/archives/1692)
