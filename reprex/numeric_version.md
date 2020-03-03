``` r
numeric_version("1.23-456")
#> [1] '1.23.456'
utils::packageVersion("tibble")
#> [1] '2.1.3'
getRversion()
#> [1] '3.6.3'

numeric_version("1.2") < numeric_version("1.3")
#> [1] TRUE
numeric_version("1.23") < numeric_version("1.3")
#> [1] FALSE

numeric_version("1.2")[NA]
#> [1] <NA>
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
