``` r
library(dialr)

# Parse a character phone number vector
x <- c(0, 0123, "0404 753 123", "61410123817", "+12015550123")
x <- phone(x, "AU")

print(x)
#> # Parsed phone numbers: 5 total, 4 successfully parsed
#> [1] 0            123          0404 753 123 61410123817  +12015550123

is_parsed(x)    # Was the phone number successfully parsed?
#> [1] FALSE  TRUE  TRUE  TRUE  TRUE
is_valid(x)     # Is the phone number valid?
#> [1] FALSE FALSE  TRUE  TRUE  TRUE
is_possible(x)  # Is the phone number possible?
#> [1] FALSE FALSE  TRUE  TRUE  TRUE
get_region(x)   # What region (ISO country code) is the phone number from?
#> [1] NA   NA   "AU" "AU" "US"
get_type(x)     # Is the phone number a fixed line, mobile etc.
#> [1] NA                     "UNKNOWN"              "MOBILE"              
#> [4] "MOBILE"               "FIXED_LINE_OR_MOBILE"
format(x)
#> [1] NA             "+61123"       "+61404753123" "+61410123817" "+12015550123"
format(x, home = "AU")
#> [1] NA                "123"             "0404753123"      "0410123817"     
#> [5] "001112015550123"

# Use with dplyr
library(dplyr)

y <- tibble(id = 1:4,
            phone1 = c(0, 0123, "0404 753 123", "61410123817"),
            phone2 = c("03 9388 1234", 1234, "+12015550123", 0),
            country = c("AU", "AU", "AU", "AU"))

y %>%
  mutate_at(vars(matches("^phone")), ~phone(., country)) %>%
  mutate_at(vars(matches("^phone")),
            list(valid = is_valid,
                 region = get_region,
                 type = get_type,
                 clean = format))
#> # A tibble: 4 x 12
#>      id       phone1       phone2 country phone1_valid phone2_valid
#>   <int>      <phone>      <phone> <chr>   <lgl>        <lgl>       
#> 1     1           NA +61393881234 AU      FALSE        TRUE        
#> 2     2       +61123      +611234 AU      FALSE        FALSE       
#> 3     3 +61404753123 +12015550123 AU      TRUE         TRUE        
#> 4     4 +61410123817           NA AU      TRUE         FALSE       
#> # … with 6 more variables: phone1_region <chr>, phone2_region <chr>,
#> #   phone1_type <chr>, phone2_type <chr>, phone1_clean <chr>,
#> #   phone2_clean <chr>
```

<sup>Created on 2021-02-27 by the [reprex package](https://reprex.tidyverse.org) (v1.0.0)</sup>
