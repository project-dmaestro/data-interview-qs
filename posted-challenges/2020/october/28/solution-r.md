---
layout: default
---

# Solution in R

### Pre-processing Data

**First, import the required libraries.** I'll be using `tidyverse` as the basic package and I'll add more packages along the way as needed. I choose to suppress the [diagnostic messages](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/message), hence the `suppressPackageStartupMessages()`. Loading the library without the suppression, `library(tidyverse)`, like so works as well.

```r
suppressPackageStartupMessages(library(tidyverse))
```

**Next, import the CSV file using `read.csv()`.** After every import, **always** check if the file is imported correctly (i.e. no parsing error, correct column names, correct data type, each variable has its own column, each observation has its own cell).

When importing the file into the `dataset` variable, there's a parsing error in the `desc` variable; 40 rows have characters in them though `desc` is specified as _numeric_. Further description to an error while reading a file can be checked using `problems()`. To fix the error, I utilize the `colClasses()` parameter by defining `desc` column as _character_. It won't have any significant effect to how I'd process the data seeing that the _numeric_ values were only zeroes. It'd also be logical to change the column's data type since "desc" is short for "description". `read_csv()` doesn't have `colClasses()` parameter though I'd imagine it'd load this large dataset faster.

```r
dataset <- read.csv("trunc_loan_data.csv",
                    colClasses= c("desc" = "character"))
```

Now that the file has been read properly, let's check for more errors. The `str()` gives "structure" of the desired object. If applied towards a name of a dataset, it'd give descriptions about a dataset's column name(s) and column type(s).

```r
str(dataset)
```

The imported file is missing a column name. The first column is supposed to be `zip_code` but it doesn't exist in the original file. R naturally replaces the missing column name with `X` or `X1`, with the number signifiying the n-th missing column name. That needs to be taken care of before moving forward.

```r
colnames(dataset)[1] <- c("zip_code")
```

Notice that some columns don't have its correct data type, particularly columns that are supposed to be _Date_ objects such as: `earliest_cr_line`, `issued_d`, `last_credit_pull_d`, `last_pymnt_d` and `next_pymnt_d`.

### Data Manipulation

Now that the data has been processed, I can start playing with the data.

**First, create a `loan_status_type` column by categorizing `loan_status` into "Closed" or "Current".** The `loan_status_type` has six statuses which are **Fully Paid**, **Current**, [**Charged Off**](https://en.wikipedia.org/wiki/Charge-off), **Late (16 - 30 days)**, **Late (31 - 120 days)**, **In Grace Period** and [**Default**](https://www.investopedia.com/terms/d/default2.asp). In this case, **Fully Paid** is categorized as **Closed** while other categories are considered **Current**. By combining functionalities of `mutate()` and `if_else()`, the newly created `loan_status_type_` will be the last column added into the `dataset` variable.

```r
dataset <- dataset %>% mutate(
  loan_status_type = if_else(loan_status == "Fully Paid",
                             "Closed",
                             "Current"))
```

**Next, create a `loan_status_standing` column by categorizing `loan_status` into "Good" or "Bad" customers.** In this case, **Fully Paid** is categoized as **Good** while other categories are considered **Bad**. Create `loan_status_standing` using the same method in the previous code chuck.

```r
dataset <- dataset %>% mutate(
  loan_status_standing = if_else(loan_status == "Fully Paid",
                             "Good",
                             "Bad"))
```
**Finally, plotting month and year the loan was issued and the sum of the loan amounts by loan_status_type**. The challenge seems to have entered incorrect information as the dataset doesn't have `loan_status_contract` nor is there any description of what the column is, should I create one. The column `issue_d` shows when the loan was funded and the 
column `loan_amnt` shows the amount of the loan applied for by the borrower and any deduction made by the credit department.

[back](challenge.md)
