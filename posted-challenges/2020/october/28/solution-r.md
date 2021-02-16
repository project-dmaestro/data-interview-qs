# Solution in R

First, import the required libraries. I'll be using `tidyverse` as the basic package and I'll add more packages along the way as needed. I choose to suppress the [diagnostic messages](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/message), hence the `suppressPackageStartupMessages()`. Loading the library without the suppression, `library(tidyverse)`, like so works as well.

```markdown
suppressPackageStartupMessages(library(tidyverse))
```

Next, import the CSV file using `read.csv`. [One source](http://yetanothermathprogrammingconsultant.blogspot.com/2016/12/reading-csv-files-in-r-readcsv-vs.htmlhttp://yetanothermathprogrammingconsultant.blogspot.com/2016/12/reading-csv-files-in-r-readcsv-vs.html) says that `read_csv` from `readr` package loads the file as R dataframe which works great for large files, while `read.csv` loads the file as tibble. However, the reason I'm using `read.csv` is because there's a parsing error in the `desc` variable; 40 rows have characters in them though `desc` is specified as numeric column type. I can check using `problem()` to see what kind of error does the dataset have once imported into the environment. To fix the error, I use `read.csv` which has parameter `colClasses` that can be used to define a column's datatype among [other functions](https://www.r-bloggers.com/2013/09/using-colclasses-to-load-data-more-quickly-in-r/).

```markdown
dataset <- read.csv("trunc_loan_data.csv",
                    colClasses= c("desc"="character"))
```

[back](challenge.md)
