---
layout: default
---

# Solution in R

### Pre-processing Data

First, import the required libraries. I'll be using `tidyverse` as the core package and I'll add more packages along the way as needed, but it's very unlikely for daily data analyses. I choose to suppress the [diagnostic messages](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/message), hence the `suppressPackageStartupMessages()`. Loading the library without the suppression, `library(tidyverse)`, like so works as well.

```r
suppressPackageStartupMessages(library(tidyverse))
```

Next, import the CSV file using `read.csv()`. After every import, **always** check if the file is imported correctly (i.e. no parsing error, correct column name(s), correct data type(s), each variable has its own column, each observation has its own cell).
