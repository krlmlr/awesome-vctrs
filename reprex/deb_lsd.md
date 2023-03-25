``` r
library(debkeepr)

# £10 6s. 8d., £8 13s. 4d., and £5 8s. 10d. sterling
deb_lsd(l = c(10, 8, 5),
        s = c(6, 13, 8),
        d = c(8, 4, 10))
#> <deb_lsd[3]>
#> [1] 10:6s:8d 8:13s:4d 5:8s:10d
#> # Bases: 20s 12d

# Alternate bases: 345 hundredweight 1 quarter 8 lbs
deb_lsd(345, 1, 8, bases = c(4, 28))
#> <deb_lsd[1]>
#> [1] 345:1s:8d
#> # Bases: 4s 28d

# Ability to do arithmetic with non-decimal currencies

# Sum of lsd values
sum(deb_lsd(l = c(28, 32, 54, 18),
            s = c(15, 8, 18, 12),
            d = c(8, 11, 7, 9)))
#> <deb_lsd[1]>
#> [1] 134:15s:11d
#> # Bases: 20s 12d

# Multiply £15 3s. 8d. sterling by 32
deb_lsd(15, 3, 8) * 32
#> <deb_lsd[1]>
#> [1] 485:17s:4d
#> # Bases: 20s 12d

# Divide 345 hundredweight 1 quarter 8 lbs by 22
deb_lsd(345, 1, 8, bases = c(4, 28)) / 22
#> <deb_lsd[1]>
#> [1] 15:2s:22d
#> # Bases: 4s 28d

# Transaction data frame, mimicking a double-entry bookkeeping account book
df <- data.frame(
  credit = c(1, 3, 2, 2, 3),
  debit  = c(3, 2, 1, 3, 1),
  lsd = deb_lsd(l = sample(20:100, 5),
                s = sample(1:19, 5),
                d = sample(1:11, 5))
)
df
#>   credit debit        lsd
#> 1      1     3  43:13s:1d
#> 2      3     2  70:17s:4d
#> 3      2     1 87:10s:11d
#> 4      2     3  60:11s:3d
#> 5      3     1   94:3s:9d

# Summary of total credit, total debit, and current value of accounts
deb_account_summary(df, credit = credit, debit = debit, lsd = lsd)
#>   account_id    credit      debit      current
#> 1          1 43:13s:1d 181:14s:8d -138:-1s:-7d
#> 2          2 148:2s:2d  70:17s:4d    77:4s:10d
#> 3          3 165:1s:1d  104:4s:4d    60:16s:9d


# Casting with deb_decimal and deb_tetra type vectors

# To deb_decimal
deb_as_decimal(deb_lsd(8, 13, 4))
#> <deb_decimal[1]>
#> [1] 8.666667
#> # Unit: libra
#> # Bases: 20s 12d

# From deb_decimal
deb_as_lsd(deb_decimal(c(5.25, 3.825, 8.5)))
#> <deb_lsd[3]>
#> [1] 5:5s:0d  3:16s:6d 8:10s:0d
#> # Bases: 20s 12d

# To deb_tetra
deb_as_tetra(deb_lsd(8, 13, 4), f = 4)
#> <deb_tetra[1]>
#> [1] 8:13s:4d:0f
#> # Bases: 20s 12d 4f
```

<sup>Created on 2023-03-23 with [reprex v2.0.2](https://reprex.tidyverse.org)</sup>
