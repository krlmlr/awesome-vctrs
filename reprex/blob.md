``` r
library(blob)

blob(serialize(1:3, NULL), charToRaw("some string"))
#> <blob[2]>
#> [1] blob[133 B] blob[11 B]
as_blob(list(raw(3), raw(5), raw(1000)))
#> <blob[3]>
#> [1] blob[3 B]  blob[5 B]  blob[1 kB]

blob(NULL)
#> <blob[1]>
#> [1] <NA>
```

<sup>Created on 2020-03-03 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
