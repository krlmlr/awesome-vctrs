``` r
library(biblids)
# this is the hard way to enter
doi(
  prefix = c("10.1038", "10.1000", "10.1007"),
  suffix = c("nphys1170", NA, "978-3-642-65840-2_5")
)
#> <digital object identifier[3]>
#> [1] 10.1038/nphys1170          
#> [2] <NA>                       
#> [3] 10.1007/978-3-642-65840-2_5
```

There's a `knit.print()` method, too:

-   [`https://doi.org/10.1038/nphys1170`](https://doi.org/10.1038/nphys1170)
-   `NA`
-   [`https://doi.org/10.1007/978-3-642-65840-2_5`](https://doi.org/10.1007/978-3-642-65840-2_5)

``` r
# much easier to enter this way
as_doi(c(
  # example DOIs are from https://www.doi.org/demos.html
  "10.1594/PANGAE.726855",
  " 10.1594/GFZ.GEOFON.gfz2009kciu ", # leading/trailing spaces are removed
  "https://doi.org/10.1000/182", # URL form is parsed
  "doi:10.1000/7", # DOI from is parsed
  "foo bar", # returns NA
  NA_character_ # returns NA
))
#> <digital object identifier[6]>
#> [1] 10.1594/PANGAE.726855         
#> [2] 10.1594/GFZ.GEOFON.gfz2009kciu
#> [3] 10.1000/182                   
#> [4] 10.1000/7                     
#> [5] <NA>                          
#> [6] <NA> 

# DOIs are case insensitive and are compared as such
unique(as_doi(c("10.1000/foo", "10.1000/fOo")))
#> <digital object identifier[1]>
#> [1] 10.1000/foo

# convert back to a (normalised) character
as.character(as_doi("10.1000/zap"))
#> [1] "10.1000/zap"

# run some checks
is_doi(as_doi("10.1000/1"))
#> [1] TRUE
is_doi(1L)
#> [1] FALSE
is_doi_ish(" 10.1000/1 lorem")
#> [1] TRUE

# some extra pretty printing in tibbles
tibble::tibble(c(doi_examples(na.rm = FALSE)[1:3]))
#> # A tibble: 3 x 1
#>   `c(doi_examples(na.rm = FALSE)[1:3])`
#>   <doi>                                
#> 1 10.1038/nphys1170                    
#> 2 NA                                   
#> 3 10.1007/978-3-642-65840-2_5
```

<sup>Created on 2021-07-14 by the [reprex package](https://reprex.tidyverse.org) (v2.0.0)</sup>
