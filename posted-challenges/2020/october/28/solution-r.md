# Solution in R

**First, import the required libraries.** I'll be using `tidyverse` as the basic package and I'll add more packages along the way as needed. I choose to suppress the [diagnostic messages](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/message), hence the `suppressPackageStartupMessages()`. Loading the library without the suppression, `library(tidyverse)`, like so works as well.

```r
suppressPackageStartupMessages(library(tidyverse))
```

**Next, import the CSV file using `read.csv()`.** When importing the file into the `dataset` variable, there's a parsing error in the `desc` variable; 40 rows have characters in them though `desc` is specified as numeric column type. To fix the error, I utilize the `colClasses()` parameter by defining `desc` column's data type. `read_csv()` doesn't have that parameter though I'd imagine it'd load this large dataset faster.

```r
dataset <- read.csv("trunc_loan_data.csv",
                    colClasses= c("desc"="character"))
```

**Next, create a `loan_status_type` column by categorizing `loan_status` into "Closed" or "Current".** The `loan_status_type` has six statuses which are **Fully Paid**, **Current**, [**Charged Off**](https://en.wikipedia.org/wiki/Charge-off), **Late (16 - 30 days)**, **Late (31 - 120 days)**, **In Grace Period** and [**Default**](https://www.investopedia.com/terms/d/default2.asp). In this case, **Fully Paid** is categorized as **Closed** while others are considered **Current**. By combining functionalities of `mutate()` and `if_else()`, the newly created `loan_status_type_` will be the last column added into the `dataset` variable.

```r
dataset <- dataset %>% mutate(
  loan_status_type = if_else(loan_status == "Fully Paid",
                             "Closed",
                             "Current"))
```

*Next, create a 

[back](challenge.md)
