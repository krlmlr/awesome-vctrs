``` r
library(decimal)

x <- decimal(c("0.1", "0.2", "0.3"))
x
#> <decimal[3]>
#> [1] 0.1 0.2 0.3

# Binary floating point cannot represent these exactly
0.1 + 0.2 == 0.3
#> [1] FALSE

sum(x[1:2]) == x[3]
#> [1] TRUE

# Arithmetic is governed by an explicit context
get_decimal_context()
#> <decimal_context>
#>   precision: 28
#>   rounding:  half_even
#>   emin:      -999999
#>   emax:      999999
#>   clamp:     FALSE
#>   traps:     [division_by_zero, invalid_operation, overflow]
#>   flags:     []

# Scale is preserved, so trailing zeros are meaningful
decimal("1.50") * decimal("2")
#> <decimal[1]>
#> [1] 3.00

# Combines and casts through vctrs
c(x, decimal("4.5"))
#> <decimal[4]>
#> [1] 0.1 0.2 0.3 4.5

tibble::tibble(price = x, qty = 1:3)
#> # A tibble: 3 × 2
#>   price   qty
#>   <dec> <int>
#> 1   0.1     1
#> 2   0.2     2
#> 3   0.3     3

NA_decimal_
#> <decimal[1]>
#> [1] <NA>
```

<sup>Created on 2026-09-19 with [reprex v2.1.1](https://reprex.tidyverse.org)</sup>
