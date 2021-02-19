``` r
library("era")

# A yr is a vector of years with an associated 'era'
yr(2011:2020, "CE")
#> # CE years <yr[10]>:
#>  [1] 2011 2012 2013 2014 2015 2016 2017 2018 2019 2020
#> # Era: Common Era (CE): Gregorian years (365.2425 days), counted forwards from 0

# Many year numbering systems are built into the package
this_year("AH")
#> # AH years <yr[1]>:
#> [1] 1443
#> # Era: Anno Hegirae (AH): Islamic lunar years (354.36708 days), counted forwards from 621.539367680377
this_year("SH")
#> # SH years <yr[1]>:
#> [1] 1399
#> # Era: Solar Hijri (SH): Nowruz years (365.2424 days), counted forwards from 622.221770467566
this_year("BP")
#> # BP years <yr[1]>:
#> [1] -71
#> # Era: Before Present (BP): Gregorian years (365.2425 days), counted backwards from 1950

# Others can be defined by the user
third_age <- era("T.A.", epoch = -9021, name = "Third Age", direction = 1)
yr(3021, third_age)
#> # T.A. years <yr[1]>:
#> [1] 3021
#> # Era: Third Age (T.A.): Gregorian years (365.2425 days), counted forwards from -9021

# yr_transform() converts between any two eras
x <- yr(10000, "BCE")
yr_transform(x, "BP", precision = 100)
#> # BP years <yr[1]>:
#> [1] 12000
#> # Era: Before Present (BP): Gregorian years (365.2425 days), counted backwards from 1950
yr_transform(x, "ka", precision = 1)
#> # ka years <yr[1]>:
#> [1] 12
#> # Era: kiloannum (ka): 1000 Gregorian years (365.2425 days), counted backwards from 1950
yr_transform(x, third_age)
#> # T.A. years <yr[1]>:
#> [1] -979
#> # Era: Third Age (T.A.): Gregorian years (365.2425 days), counted forwards from -9021

# yr vectors look good in tibbles
tibble::tribble(
  ~period,           ~start_ka,
  "Late Holocene",   4.2,
  "Mid Holocene",    8.326,
  "Early Holocene",  11.7,
  "Younger Dryas",   12.9,
  "Bølling-Allerød", 14.7,
  "Heinrich 1",      17.0
) %>% 
  dplyr::mutate(start_ka = yr(start_ka, "ka"))
#> # A tibble: 6 x 2
#>   period          start_ka
#>   <chr>               <yr>
#> 1 Late Holocene     4.2 ka
#> 2 Mid Holocene    8.326 ka
#> 3 Early Holocene   11.7 ka
#> 4 Younger Dryas    12.9 ka
#> 5 Bølling-Allerød  14.7 ka
#> 6 Heinrich 1         17 ka
```

<sup>Created on 2021-02-05 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>