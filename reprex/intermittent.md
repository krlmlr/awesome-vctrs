``` r
library(intermittent)
x <- term(2123, origin = "cs")
x
#> <term[1]>
#> [1]  2123
attributes(x)
#> $origin
#> [1] "cs"
#>
#> $class
#> [1] "term"       "vctrs_vctr"

### Increment the term
x + 1 # To Fall 2012
#> <term[1]>
#> [1]  2127
x + 2 # To Spring 2013
#> <term[1]>
#> [1]  2133
x + 5 # To Fall 2014
#> <term[1]>
#> [1]  2147

x - 1 # To Fall 2011
#> <term[1]>
#> [1]  2117
x - 3 # To Fall 2010
#> <term[1]>
#> [1]  2107

### Comparison
y <- term(2133, "cs")
x < y
#> [1] TRUE

grad_term <- term(20182, "sims") # Spring 2018
matric_term <- term(20144, "sims") # Fall 2014
grad_term - matric_term
#> [1] 8

label_term(x)
#> [1] "Spring 2012"
acad_year(x)
#> [1] "2011-12"
cal_year(x)
#> [1] 2012

# Fall 2010 to Spring 2016 with a "sims" origin
sims_terms <- seq(term(20104), 20162)
sims_terms
#> <term[12]>
#>  [1] 20104 20112 20114 20122 20124 20132 20134 20142 20144 20152 20154 20162

min(sims_terms)
#> <term[1]>
#> [1]  20104
max(sims_terms)
#> <term[1]>
#> [1]  20162
median(sims_terms) # Retrieve the 'middle' term
#> <term[1]>
#> [1] 20132
range(sims_terms) # Retrieve the min/max
#> <term[2]>
#> [1]  20104  20162

library(dplyr)
#>
#> Attaching package: 'dplyr'
#> The following objects are masked from 'package:stats':
#>
#>     filter, lag
#> The following objects are masked from 'package:base':
#>
#>     intersect, setdiff, setequal, union
library(tibble)

tibble(term = c(2123, 2127, 2133, 2137)) %>%
  mutate(
    term = as_term(term, "cs"),
    second_term = term + 1,
    grad_term = as_term(2163, "cs"),
    terms_to_degree = grad_term - term, # or term_duration(grad_term, term)
    term_label = label_term(term),
    academic_year = acad_year(term),
    year = cal_year(term)
  )
#> Warning in if (is.na(x)) return(NA): the condition has length > 1 and only the
#> first element will be used
#> Warning in if (is.na(y)) return(NA): the condition has length > 1 and only the
#> first element will be used
#> # A tibble: 4 x 7
#>     term second_term grad_term terms_to_degree term_label  academic_year  year
#>   <term>      <term>    <term>           <int> <chr>       <chr>         <dbl>
#> 1   2123        2127      2163               9 Spring 2012 2011-12        2012
#> 2   2127        2133      2163               8 Fall 2012   2012-13        2012
#> 3   2133        2137      2163               7 Spring 2013 2012-13        2013
#> 4   2137        2143      2163               6 Fall 2013   2013-14        2013

fall16 <- term(2167, origin = "cs")
spring20 <- term(2203, origin = "cs")
label_term(fall16)
#> [1] "Fall 2016"
label_term(spring20)
#> [1] "Spring 2020"

# Get next 5 terms
label_term(get_next(fall16, 5))
#> [1] "Fall 2016"   "Spring 2017" "Fall 2017"   "Spring 2018" "Fall 2018"
#> [6] "Spring 2019"

# Get last 5 terms
label_term(get_last(spring20, 5))
#> [1] "Fall 2017"   "Spring 2018" "Fall 2018"   "Spring 2019" "Fall 2019"
#> [6] "Spring 2020"

# Get next 5 fall terms
label_term(fall16 %+F% 5)
#> [1] "Fall 2016" "Fall 2017" "Fall 2018" "Fall 2019" "Fall 2020" "Fall 2021"

# Get last 5 spring terms
label_term(spring20 %-S% 5)
#> [1] "Spring 2015" "Spring 2016" "Spring 2017" "Spring 2018" "Spring 2019"
#> [6] "Spring 2020"

getOption("intermittent.use_terms")
#> [1] "fasp"
seq(term(2127, "cs"), 2173)
#> <term[10]>
#>  [1] 2127 2133 2137 2143 2147 2153 2157 2163 2167 2173

# Include summer terms
options(intermittent.use_terms = "all")
seq(term(2127, "cs"), 2173)
#> <term[14]>
#>  [1] 2127 2133 2135 2137 2143 2145 2147 2153 2155 2157 2163 2165 2167 2173
```

<sup>Created on 2021-12-22 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
