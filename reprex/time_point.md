``` r
library(clock)

x <- naive_time_parse("2019-01-01 01:02:03.12345", precision = "microsecond")
x
#> <time_point<naive><microsecond>[1]>
#> [1] "2019-01-01 01:02:03.123450"

x + duration_hours(5:6)
#> <time_point<naive><microsecond>[2]>
#> [1] "2019-01-01 06:02:03.123450" "2019-01-01 07:02:03.123450"

as_zoned_time(x, "America/New_York")
#> <zoned_time<microsecond><America/New_York>[1]>
#> [1] "2019-01-01 01:02:03.123450-05:00"
as_zoned_time(x, "Europe/London")
#> <zoned_time<microsecond><Europe/London>[1]>
#> [1] "2019-01-01 01:02:03.123450+00:00"

time_point_floor(x, "hour")
#> <time_point<naive><hour>[1]>
#> [1] "2019-01-01 01"

as_year_month_weekday(x)
#> <year_month_weekday<microsecond>[1]>
#> [1] "2019-01-Tue[1] 01:02:03.123450"
```

<sup>Created on 2021-04-06 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
