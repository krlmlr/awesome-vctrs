``` r
library(dint)

date_y(2020)
#> [1] "2020"
date_ym(2020, 2:4)
#> [1] "2020-M02" "2020-M03" "2020-M04"
date_yq(2020, 1:2)
#> [1] "2020-Q1" "2020-Q2"
date_yw(2020, 9:12)
#> [1] "2020-W09" "2020-W10" "2020-W11" "2020-W12"

date_ym(2020, 2:4) + 5
#> [1] "2020-M07" "2020-M08" "2020-M09"
date_yq(2020, 1) + 2
#> [1] "2020-Q3"

date_y(NA)
#> [1] "NA"
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
