``` r
library(intrval)
x <- rep(4, 5)
a <- 1:5
b <- 3:7
cbind(x=x, a=a, b=b)
#>      x a b
#> [1,] 4 1 3
#> [2,] 4 2 4
#> [3,] 4 3 5
#> [4,] 4 4 6
#> [5,] 4 5 7
x %[]% cbind(a, b) # matrix
#> [1] FALSE  TRUE  TRUE  TRUE FALSE
x %[]% data.frame(a=a, b=b) # data.frame
#> [1] FALSE  TRUE  TRUE  TRUE FALSE
x %[]% list(a, b) # list
#> [1] FALSE  TRUE  TRUE  TRUE FALSE
```

<sup>Created on 2022-07-14 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
