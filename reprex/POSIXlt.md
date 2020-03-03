``` r
time <- strptime("2020-03-03 09:29:45", "%F %T")

time
#> [1] "2020-03-03 09:29:45 CET"
time + 1:3
#> [1] "2020-03-03 09:29:46 CET" "2020-03-03 09:29:47 CET"
#> [3] "2020-03-03 09:29:48 CET"
as.POSIXlt(Sys.time())
#> [1] "2020-03-03 09:37:30 CET"
time[NA]
#> [1] NA
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
