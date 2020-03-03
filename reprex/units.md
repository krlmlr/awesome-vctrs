``` r
library(units)
#> udunits system database from /usr/share/xml/udunits

set_units(1:3, m)
#> Units: [m]
#> [1] 1 2 3
set_units(60, km / h) * set_units(5, min)
#> 5 [km]
set_units(50, km / h) / set_units(9.81, m / s^2)
#> 1.415789 [s]
set_units(NA, m)
#> NA [m]
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
