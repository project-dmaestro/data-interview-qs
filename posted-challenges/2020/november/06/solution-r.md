---
layout: default
---

# solution

First step was to import the required libraries. I used ```tidyverse``` as the core package and would be adding more packages along the way as needed. Turned out that the downloaded dataset from the website was in xlsx extension, so I added another package ```readxl```.

```
suppressPackageStartupMessages(library(tidyverse))
suppressPackageStartupMessages(library(readxl))
```

Next step was to import the downloaded dataset into R IDE.

```
dataset <- read_excel("archigos-mar-2016.xlsx")
```

The challenge describes a variable named `endyear` for the plot's x-axis which doesn't exist. Thus, I did a little data manipulation to extract the `endyear`.
