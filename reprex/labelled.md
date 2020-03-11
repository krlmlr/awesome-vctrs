``` r
library(haven)
library(forcats)

# Main use: data sets imported by read_spss, read_dta & read_sas.
# Toy example:
x <- labelled(c(3, 1, 2),
              label  = "Do you like R?",
              labels = c("Very much."  = 1,
                         "So so."      = 2,
                         "Not at all." = 3))

x
#> <Labelled double>: Do you like R?
#> [1] 3 1 2
#> 
#> Labels:
#>  value       label
#>      1  Very much.
#>      2      So so.
#>      3 Not at all.

attr(x, "label")
#> [1] "Do you like R?"

attr(x, "labels")
#>  Very much.      So so. Not at all. 
#>           1           2           3

x %>% as_factor()
#> [1] Not at all. Very much.  So so.     
#> attr(,"label")
#> [1] Do you like R?
#> Levels: Very much. So so. Not at all.

x %>% as.numeric()
#> [1] 3 1 2

x %>% as_factor() %>% as.character()
#> [1] "Not at all." "Very much."  "So so."

x[x != 1] <- 1

x
#> <Labelled double>: Do you like R?
#> [1] 1 1 1
#> 
#> Labels:
#>  value       label
#>      1  Very much.
#>      2      So so.
#>      3 Not at all.

# Also character vectors can be labelled:
labelled(c("M", "M", "F"), c(Male = "M", Female = "F"))
#> <Labelled character>
#> [1] M M F
#> 
#> Labels:
#>  value  label
#>      M   Male
#>      F Female
```

<sup>Created on 2020-03-11 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
