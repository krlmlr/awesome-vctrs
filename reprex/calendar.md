``` r
library(clock)

year_month_day(2019:2020, 2, "last")
#> <year_month_day<day>[2]>
#> [1] "2019-02-28" "2020-02-29"

year_quarter_day(2020, 1:3, 22)
#> <year_quarter_day<January><day>[3]>
#> [1] "2020-Q1-22" "2020-Q2-22" "2020-Q3-22"
as.Date(year_quarter_day(2020, 1:3, 22))
#> [1] "2020-01-22" "2020-04-22" "2020-07-22"

# "2nd Sunday in January"
year_month_weekday(2020, 1, clock_weekdays$sunday, 2)
#> <year_month_weekday<day>[1]>
#> [1] "2020-01-Sun[2]"
as.Date(year_month_weekday(2020, 1, clock_weekdays$sunday, 2))
#> [1] "2020-01-12"
```

<sup>Created on 2021-04-06 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
