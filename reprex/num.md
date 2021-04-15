``` r
library(pillar)

num(8:12 * 100 + 0.5, digits = 4)
#> <pillar_num:.4![5]>
#> [1]  800.5000  900.5000 1000.5000 1100.5000 1200.5000
num(8:12 * 100 + 0.5, digits = -1)
#> <pillar_num:.1[5]>
#> [1]  800.5  900.5 1000.5 1100.5 1200.5
num(8:12 * 100 + 0.5, digits = 2, label = "USD")
#> <pillar_num:.2!{USD}[5]>
#> [1]  800.50  900.50 1000.50 1100.50 1200.50
num(8:12 / 100 + 0.0005, label = "%", scale = 100)
#> <pillar_num{%}*100[5]>
#> [1]  8.05  9.05 10.0  11.0  12.0
num(10^(-3:1), notation = "eng", fixed_exponent = -Inf)
#> <pillar_num(eng)|-Inf[5]>
#> [1]     1e-3    10e-3   100e-3  1000e-3 10000e-3
num(10^(-3:1) * 123, notation = "si")
#> <pillar_num(si)[5]>
#> [1] 123   m   1.23   12.3   123       1.23k

num(1) + 2
#> <pillar_num[1]>
#> [1] 3
1 + num(2)
#> <pillar_num[1]>
#> [1] 3
1L + num(2)
#> <pillar_num[1]>
#> [1] 3
num(3.23456, sigfig = 4) - num(2)
#> <pillar_num:4[1]>
#> [1] 1.235
num(4, sigfig = 2) * num(3, digits = 2)
#> <pillar_num:2[1]>
#> [1] 12
num(3, digits = 2) * num(4, sigfig = 2)
#> <pillar_num:.2![1]>
#> [1] 12.00
-num(2)
#> <pillar_num[1]>
#> [1] -2

mean(num(1:3, notation = "eng"))
#> <pillar_num(eng)[1]>
#> [1] 2e0
```

<sup>Created on 2021-04-15 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
