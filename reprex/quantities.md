``` r
library(quantities)
#> Loading required package: units
#> udunits database from /usr/share/udunits/udunits2.xml
#> Loading required package: errors

set_quantities(1:3, m, 0.1)
#> Units: [m]
#> Errors: 0.1 0.1 0.1
#> [1] 1 2 3
set_quantities(60, km / h, 1) * set_quantities(5, min, 1/60)
#> 5.00(8) [km]
options(errors.notation="plus-minus")
set_quantities(50, km / h, 1) / set_quantities(9.81, m / s^2, 0.045)
#> 1.42 ± 0.03 [s]

set_quantities(NA_real_, m, 0.3)
#> NA ± NA [m]
```

<sup>Created on 2021-03-14 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
