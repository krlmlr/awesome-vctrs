``` r
library(tf)
#> 
#> Attaching package: 'tf'
#> The following objects are masked from 'package:stats':
#> 
#>     sd, var

x <- rnorm(10)
tfb(x)
#> Percentage of input data variability preserved in basis representation
#> (per functional observation, approximate):
#>    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
#>      14      14      14      14      14      14
#> tfb[1] on (1,10) in basis representation:
#>  using  s(arg, bs = "cr", k = 10) 
#> [1]: (1,-0.2);(2,-0.5);(3,-0.7); ...
```

<sup>Created on 2024-01-05 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
