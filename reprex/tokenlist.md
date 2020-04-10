``` r
stopifnot(packageVersion("textrecipes") >= "0.1.0.9000")
library(textrecipes)

x <- tokenlist(list(letters[1:3], LETTERS[4:6], letters[9:8]))

x
#> <textrecipes_tokenlist[3]>
#> [1] [3 tokens] [3 tokens] [2 tokens]
#> # Unique Tokens: 8
x[1:2]
#> <textrecipes_tokenlist[2]>
#> [1] [3 tokens] [3 tokens]
#> # Unique Tokens: 6
```

<sup>Created on 2020-04-10 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
