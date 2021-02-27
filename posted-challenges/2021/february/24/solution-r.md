# solution in R

## designing the code

## coding
First step was to import the required libraries. I used `tidyverse` as the core package and would be adding more packages along the way as needed. I set an arbitrary as seed for the random number generator.

```r
suppressPackageStartupMessages(library(tidyverse))
set.seed(42)
```

Next, I defined a function to sort randomly generated numbers alternately between great and small numbers.

```r
# param:  the minimum value
#         the maximum value
#         the number of generated numbers
#
# return: print of generated values
#         print of sorted values
alter_sort = function(min,max,n){
  generated = sort(sample(c(min:max),n))
  
  front = 1 # index counting forward
  back = length(generated) # index counting backward
  
  sorted = c() # initialize empty vector
  while(front < back){
    sorted = c(sorted,generated[back],generated[front]) # merge previous vector with sorted values
    
    # updating index value
    front = front + 1
    back = back - 1
  }
  
  if(n%%2 != 0){
    sorted = c(sorted,generated[back])
  }
  
  cat(c("generated numbers \t:","[",generated,"]\n"))
  cat(c("sorted numbers \t\t:","[",sorted,"]","\n\n"))
}
```
