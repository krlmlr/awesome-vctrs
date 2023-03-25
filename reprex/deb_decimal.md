``` r
library(debkeepr)

# £8 16s. 6d. sterling as decimalized pounds
deb_decimal(8.825)
#> <deb_decimal[1]>
#> [1] 8.825
#> # Unit: libra
#> # Bases: 20s 12d

# £8 16s. 6d. sterling as decimalized shillings
deb_decimal(8.825, unit = "s")
#> <deb_decimal[1]>
#> [1] 8.825
#> # Unit: solidus
#> # Bases: 20s 12d

# £8 16s. 6d. sterling as decimalized pence
deb_decimal(8.825, unit = "d")
#> <deb_decimal[1]>
#> [1] 8.825
#> # Unit: denarius
#> # Bases: 20s 12d

# Decimalized tripartite values with alternate bases
deb_decimal(c(5.25, 3.825, 8.5), bases = c(4, 28))
#> <deb_decimal[3]>
#> [1] 5.250 3.825 8.500
#> # Unit: libra
#> # Bases: 4s 28d

# £5 2s.4d. 2f. sterling as decimalized pounds
deb_decimal(5.11875, bases = c(20, 12, 4))
#> <deb_decimal[1]>
#> [1] 5.11875
#> # Unit: libra
#> # Bases: 20s 12d 4f

# Casting with deb_lsd and deb_tetra type vectors

# To deb_lsd
deb_as_lsd(deb_decimal(8.825))
#> <deb_lsd[1]>
#> [1] 8:16s:6d
#> # Bases: 20s 12d

# To deb_tetra
deb_as_tetra(deb_decimal(5.11875, bases = c(20, 12, 4)))
#> <deb_tetra[1]>
#> [1] 5:2s:4d:2f
#> # Bases: 20s 12d 4f

# From deb_lsd
deb_as_decimal(deb_lsd(8, 13, 4))
#> <deb_decimal[1]>
#> [1] 8.666667
#> # Unit: libra
#> # Bases: 20s 12d
```

<sup>Created on 2023-03-23 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
