``` r
library(bignum)

bigfloat(-2e34)
#> <bigfloat[1]>
#> [1] -2e+34

bigfloat("3.5e65")
#> <bigfloat[1]>
#> [1] 3.5e+65

bigfloat(1) / 3
#> <bigfloat[1]>
#> [1] 0.3333333

options(bignum.sigfig = 50)
options(bignum.max_dec_width = Inf)
bigfloat(1) / 3
#> <bigfloat[1]>
#> [1] 0.33333333333333333333333333333333333333333333333333

bigfloat(c(Inf, -Inf, NaN, NA))
#> <bigfloat[4]>
#> [1] Inf  -Inf NaN  <NA>

NA_bigfloat_
#> <bigfloat[1]>
#> [1] <NA>
```

<sup>Created on 2021-06-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.0)</sup>
