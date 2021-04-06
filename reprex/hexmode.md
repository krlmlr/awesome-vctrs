``` r
x <- as.hexmode(8:16)
x + 1
#> [1] "09" "0a" "0b" "0c" "0d" "0e" "0f" "10" "11"
x[NA_integer_]
#> [1] NA
as.hexmode(NA)
#> Error in as.hexmode(NA): 'x' cannot be coerced to class "hexmode"
as.hexmode(NA_integer_)
#> [1] NA
```

<sup>Created on 2021-04-06 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
