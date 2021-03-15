``` r
library(errors)

set_errors(1:3, 0.1)
#> Errors: 0.1 0.1 0.1
#> [1] 1 2 3
set_errors(60, 1) * set_errors(5, 0.2)
#> 300(10)
options(errors.notation="plus-minus")
set_errors(50, 3) / set_errors(9.81, 0.045)
#> 5.1 ± 0.3

set_errors(NA, 0.3)
#> NA ± NA
```

<sup>Created on 2021-03-14 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
