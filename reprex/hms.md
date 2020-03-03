``` r
library(hms)

hms(56, 34, 12)
#> 12:34:56
parse_hm("12:34")
#> 12:34:00
as_hms(parse_hms("12:34:58") + 1:3)
#> 12:34:59
#> 12:35:00
#> 12:35:01
hms(1:3 * 1e-6)
#> 00:00:00.000001
#> 00:00:00.000002
#> 00:00:00.000003
as_hms(Sys.time() - as.POSIXct(Sys.Date()))
#> 09:05:06.343932

hms(NA)
#> NA
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
