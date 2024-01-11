``` r
library(tf)
#> 
#> Attaching package: 'tf'
#> The following objects are masked from 'package:stats':
#> 
#>     sd, var

tfd(1:10)
#> tfd[1] on (1,10) based on 10 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (1,1);(2,2);(3,3); ...

# create random data
x <- tf_rgp(10)
x
#> tfd[10] on (0,1) based on 51 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (0.00,-1.06);(0.02,-1.05);(0.04,-0.95); ...

# retrieve evaluations, arg, and domain
tf_evaluations(x)[[1]]
#>  [1] -1.05791255 -1.04550286 -0.95406271 -0.92481174 -0.86481902 -0.80794455
#>  [7] -0.70702753 -0.70243817 -0.67746275 -0.66407519 -0.70032597 -0.66538820
#> [13] -0.72617132 -0.72562492 -0.76612056 -0.81472952 -0.87452733 -0.95225977
#> [19] -1.07260680 -1.06217320 -1.16575804 -1.16904437 -1.16310000 -1.17346691
#> [25] -1.13878338 -1.04360177 -0.98606220 -0.84954404 -0.74134285 -0.56117719
#> [31] -0.42304280 -0.25816989 -0.06588892  0.13700844  0.25178507  0.43043945
#> [37]  0.66885002  0.77314873  0.91916457  1.01438437  1.07322309  1.11544600
#> [43]  1.16963034  1.22580065  1.17198137  1.17273163  1.07679134  0.94270401
#> [49]  0.89171643  0.84052767  0.71306731
tf_arg(x)
#>  [1] 0.00 0.02 0.04 0.06 0.08 0.10 0.12 0.14 0.16 0.18 0.20 0.22 0.24 0.26 0.28
#> [16] 0.30 0.32 0.34 0.36 0.38 0.40 0.42 0.44 0.46 0.48 0.50 0.52 0.54 0.56 0.58
#> [31] 0.60 0.62 0.64 0.66 0.68 0.70 0.72 0.74 0.76 0.78 0.80 0.82 0.84 0.86 0.88
#> [46] 0.90 0.92 0.94 0.96 0.98 1.00
tf_domain(x)
#> [1] 0 1

# math operations
sum(x)
#> tfd[1] on (0,1) based on 51 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (0.00,1.9);(0.02,2.1);(0.04,2.5); ...
y <- tf_rgp(10)
x + y
#> tfd[10] on (0,1) based on 51 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (0.00,-1.00);(0.02,-0.84);(0.04,-0.58); ...

# interpolate missing values
x <- rnorm(10)
x[[3]] <- NA
x <- tfd(x, arg = 1:10)
tf_interpolate(x, arg = 1:10)
#> tfd[1] on (1,10) based on 10 evaluations each
#> interpolation by tf_approx_linear 
#> [1]: (1,1.2);(2,0.4);(3,0.3); ...
# change evaluator for different interpolation
tf_interpolate(x, arg = 1:10, evaluator = tf_approx_locf)
#> tfd[1] on (1,10) based on 10 evaluations each
#> interpolation by tf_approx_locf 
#> [1]: (1,1.2);(2,0.4);(3,0.4); ...
```

<sup>Created on 2024-01-11 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
