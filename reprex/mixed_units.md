``` r
library(units)
#> udunits system database from /usr/share/xml/udunits

mixed_units(set_units(1:3, m))
#> Mixed units: m (3)
#> 1 [m], 2 [m], 3 [m]
mixed_units(1:3, c("m/s", "km/h", "mg/L"))
#> Mixed units: km/h (1), m/s (1), mg/L (1)
#> 1 [m/s], 2 [km/h], 3 [mg/L]

mixed_units(NA_real_, "m")
#> Mixed units: m (1)
#> NA [m]
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
