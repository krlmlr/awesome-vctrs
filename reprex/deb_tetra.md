``` r
library(debkeepr)

# £10 6s. 8d. 2f., £8 13s. 4d. 3f., and £5 8s. 10d. 1f. sterling
deb_tetra(l = c(10, 8, 5),
          s = c(6, 13, 8),
          d = c(8, 4, 10),
          f = c(2, 3, 1))
#> <deb_tetra[3]>
#> [1] 10:6s:8d:2f 8:13s:4d:3f 5:8s:10d:1f
#> # Bases: 20s 12d 4f

# Alternate bases: 345 hundredweight 1 quarter 0 stones 8 lbs
deb_tetra(345, 1, 0, 8, bases = c(4, 2, 14))
#> <deb_tetra[1]>
#> [1] 345:1s:0d:8f
#> # Bases: 4s 2d 14f

# Ability to do arithmetic with non-decimal currencies

# Sum of tetrapartite values with alternative bases
sum(deb_tetra(l = c(1, 8, 4, 3),
              s = c(3, 0, 3, 2),
              d = c(1, 0, 1, 0),
              f = c(12, 8, 9, 3),
              bases = c(4, 2, 14)))
#> <deb_tetra[1]>
#> [1] 18:2s:0d:4f
#> # Bases: 4s 2d 14f

# Multiply £15 3s. 8d. 3f. sterling by 32
deb_tetra(15, 3, 8, 3) * 32
#> <deb_tetra[1]>
#> [1] 485:19s:4d:0f
#> # Bases: 20s 12d 4f

# Divide 345 hundredweight 1 quarter 0 stones 8 lbs by 22
deb_tetra(345, 1, 0, 8, bases = c(4, 2, 14)) / 22
#> <deb_tetra[1]>
#> [1] 15:2s:1d:8f
#> # Bases: 4s 2d 14f

# Transaction data frame, mimicking a double-entry bookkeeping account book
df <- data.frame(
  credit = c(1, 3, 2, 2, 3),
  debit  = c(3, 2, 1, 3, 1),
  tetra = deb_tetra(l = sample(20:100, 5),
                    s = sample(1:19, 5),
                    d = sample(1:11, 5),
                    f = sample(0:3, 5, replace = TRUE))
)
df
#>   credit debit        tetra
#> 1      1     3 28:10s:4d:2f
#> 2      3     2 80:7s:11d:3f
#> 3      2     1 92:19s:9d:1f
#> 4      2     3  37:8s:6d:1f
#> 5      3     1 93:16s:3d:0f

# Summary of total credit, total debit, and current value of accounts
deb_account_summary(df, credit = credit, debit = debit, lsd = tetra)
#>   account_id       credit         debit          current
#> 1          1 28:10s:4d:2f 186:16s:0d:1f -158:-5s:-7d:-3f
#> 2          2 130:8s:3d:2f  80:7s:11d:3f      50:0s:3d:3f
#> 3          3 174:4s:2d:3f 65:18s:10d:3f     108:5s:4d:0f


# Casting with deb_decimal and deb_lsd type vectors

# To deb_decimal
deb_as_decimal(deb_tetra(8, 13, 4, 3))
#> <deb_decimal[1]>
#> [1] 8.669792
#> # Unit: libra
#> # Bases: 20s 12d 4f

# From deb_decimal
deb_as_tetra(deb_decimal(c(5.11875, 3.234375, 8.2875),
                         bases = c(20, 12, 4)))
#> <deb_tetra[3]>
#> [1] 5:2s:4d:2f 3:4s:8d:1f 8:5s:9d:0f
#> # Bases: 20s 12d 4f

# To deb_lsd
deb_as_lsd(deb_tetra(8, 13, 4, 2))
#> <deb_lsd[1]>
#> [1] 8:13s:4.5d
#> # Bases: 20s 12d
```

<sup>Created on 2023-03-23 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
