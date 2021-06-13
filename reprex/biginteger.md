``` r
library(bignum)

biginteger(1:3)
#> <biginteger[3]>
#> [1] 1 2 3

biginteger(4294967296)
#> <biginteger[1]>
#> [1] 4294967296

biginteger("-18446744073709551616")
#> <biginteger[1]>
#> [1] -1.844674e+19

options(bignum.max_dec_width = Inf)
biginteger("-18446744073709551616")
#> <biginteger[1]>
#> [1] -18446744073709551616

NA_biginteger_
#> <biginteger[1]>
#> [1] <NA>
```

<sup>Created on 2021-06-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.0)</sup>
