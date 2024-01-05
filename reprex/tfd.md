``` r
library(tf)
#> 
#> Attaching package: 'tf'
#> The following objects are masked from 'package:stats':
#> 
#>     sd, var

x <- rnorm(10)
tfd(x)
#> tfd[1] on (1,10) based on 10 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (1,-0.70);(2, 0.05);(3, 1.07); ...
```

<sup>Created on 2024-01-05 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
