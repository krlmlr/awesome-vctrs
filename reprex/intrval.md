
``` r
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
#> Error in x %[]% cbind(a, b): could not find function "%[]%"
x %[]% data.frame(a=a, b=b) # data.frame
#> Error in x %[]% data.frame(a = a, b = b): could not find function "%[]%"
x %[]% list(a, b) # list
#> Error in x %[]% list(a, b): could not find function "%[]%"
```

<sup>Created on 2022-07-14 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
