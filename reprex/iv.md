``` r
library(ivs)
library(dplyr, warn.conflicts = FALSE)

x <- iv_pairs(
  c(1, 5),
  c(2, 3),
  c(5, 6),
  c(9, 12),
  c(11, 14)
)
x
#> <iv<double>[5]>
#> [1] [1, 5)   [2, 3)   [5, 6)   [9, 12)  [11, 14)

# Grouping removes all redundancy while still covering the full range
# of values that were originally represented
iv_groups(x)
#> <iv<double>[2]>
#> [1] [1, 6)  [9, 14)

# `iv_identify_group()` is useful alongside `group_by()` and `summarize()`
df <- tibble(x = x)
df <- mutate(df, group = iv_identify_group(x))
df
#> # A tibble: 5 × 2
#>           x     group
#>   <iv<dbl>> <iv<dbl>>
#> 1    [1, 5)    [1, 6)
#> 2    [2, 3)    [1, 6)
#> 3    [5, 6)    [1, 6)
#> 4   [9, 12)   [9, 14)
#> 5  [11, 14)   [9, 14)

df %>%
  group_by(group) %>%
  summarize(n = n())
#> # A tibble: 2 × 2
#>       group     n
#>   <iv<dbl>> <int>
#> 1    [1, 6)     3
#> 2   [9, 14)     2

# Interval vectors are generic, so you can use them with any type supported
# by vctrs, like dates!
x <- iv_pairs(
  as.Date(c("2019-01-05", "2019-01-10")),
  as.Date(c("2019-01-07", "2019-01-15")),
  as.Date(c("2019-01-20", "2019-01-31"))
)

y <- iv_pairs(
  as.Date(c("2019-01-01", "2019-01-03")),
  as.Date(c("2019-01-04", "2019-01-08")),
  as.Date(c("2019-01-07", "2019-01-09")),
  as.Date(c("2019-01-10", "2019-01-20")),
  as.Date(c("2019-01-15", "2019-01-20"))
)

x
#> <iv<date>[3]>
#> [1] [2019-01-05, 2019-01-10) [2019-01-07, 2019-01-15) [2019-01-20, 2019-01-31)
y
#> <iv<date>[5]>
#> [1] [2019-01-01, 2019-01-03) [2019-01-04, 2019-01-08) [2019-01-07, 2019-01-09)
#> [4] [2019-01-10, 2019-01-20) [2019-01-15, 2019-01-20)

# You can use `iv_locate_overlaps()` to find all overlaps between `x` and `y`
# in a `match()`-like way. i.e. `x[[1]]` overlaps `y[[2]]` and `y[[3]]`.
loc <- iv_locate_overlaps(x, y)
loc
#>   needles haystack
#> 1       1        2
#> 2       1        3
#> 3       2        2
#> 4       2        3
#> 5       2        4
#> 6       3       NA

# Easily align the vectors based on the overlaps
iv_align(x, y, locations = loc)
#>                    needles                 haystack
#> 1 [2019-01-05, 2019-01-10) [2019-01-04, 2019-01-08)
#> 2 [2019-01-05, 2019-01-10) [2019-01-07, 2019-01-09)
#> 3 [2019-01-07, 2019-01-15) [2019-01-04, 2019-01-08)
#> 4 [2019-01-07, 2019-01-15) [2019-01-07, 2019-01-09)
#> 5 [2019-01-07, 2019-01-15) [2019-01-10, 2019-01-20)
#> 6 [2019-01-20, 2019-01-31)                 [NA, NA)
```

<sup>Created on 2022-05-06 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
