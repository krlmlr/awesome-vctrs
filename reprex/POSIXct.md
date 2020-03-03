``` r
Sys.time()
#> [1] "2020-03-03 09:34:12 CET"
Sys.time() + 1:3
#> [1] "2020-03-03 09:34:13 CET" "2020-03-03 09:34:14 CET"
#> [3] "2020-03-03 09:34:15 CET"
as.POSIXct(strptime("2020-03-03 09:29:45", "%F %T"))
#> [1] "2020-03-03 09:29:45 CET"

Sys.time()[NA]
#> [1] NA
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
