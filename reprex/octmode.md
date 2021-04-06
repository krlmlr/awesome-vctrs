``` r
x <- as.octmode(6:10)
x + 1
#> [1] "07" "10" "11" "12" "13"
x[NA_integer_]
#> [1] NA
as.octmode(NA)
#> Error in as.octmode(NA): 'x' cannot be coerced to class "octmode"
as.octmode(NA_integer_)
#> [1] NA
```

<sup>Created on 2021-04-06 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
