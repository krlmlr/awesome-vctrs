``` r
library(tsibble)

yearquarter(c("2021 Q3", "2021 Q4"))
#> <yearquarter[2]>
#> [1] "2021 Q3" "2021 Q4"
#> # Year starts on: January
yearmonth(c("2021-10", "2021-11"))
#> <yearmonth[2]>
#> [1] "2021 Oct" "2021 Nov"
yearweek(c("2021 W40", "2021 W41"))
#> <yearweek[2]>
#> [1] "2021 W40" "2021 W41"
#> # Week starts on: Monday

yearquarter(c("2021 Q3", "2021 Q4")) + 1
#> <yearquarter[2]>
#> [1] "2021 Q4" "2022 Q1"
#> # Year starts on: January
yearmonth(c("2021-10", "2021-11")) - 2
#> <yearmonth[2]>
#> [1] "2021 Aug" "2021 Sep"
yearweek(c("2021 W40", "2021 W41")) + 3
#> <yearweek[2]>
#> [1] "2021 W43" "2021 W44"
#> # Week starts on: Monday

seq(yearmonth("2021 Oct"), length.out = 10, by = 2)
#> <yearmonth[10]>
#>  [1] "2021 Oct" "2021 Dec" "2022 Feb" "2022 Apr" "2022 Jun" "2022 Aug"
#>  [7] "2022 Oct" "2022 Dec" "2023 Feb" "2023 Apr"
```

<sup>Created on 2021-10-18 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
