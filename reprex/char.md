``` r
library(pillar)

az <- paste(letters, collapse = "")

tibble::tibble(
  full = char(az, min_chars = Inf),
  back = char(az, shorten = "back"),
  front = char(az, shorten = "front"),
  mid = char(az, shorten = "mid"),
  abbreviate = char(az, shorten = "abbreviate")
)
#> # A tibble: 1 x 5
#>   full                       back         front       mid         abbreviate
#>   <char>                     <char>       <char>      <char>      <char>
#> 1 abcdefghijklmnopqrstuvwxyz abcdefghijk… …qrstuvwxyz abcde…vwxyz abcdfghjklmnpq
```

<sup>Created on 2021-04-15 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
