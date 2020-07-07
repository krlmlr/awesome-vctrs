``` r
library(term)

term(c("alpha", "beta[1]", "beta[2]", "sigma"))
#> <term[4]>
#> [1] alpha   beta[1] beta[2] sigma

as_term(matrix(c(1,4,7,9), nrow = 2), name = "theta")
#> <term[4]>
#> [1] theta[1,1] theta[2,1] theta[1,2] theta[2,2]

term(character(0))
#> <term[0]>

term(NA_character_)
#> <term[1]>
#> [1] <NA>
```

<sup>Created on 2020-07-07 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
