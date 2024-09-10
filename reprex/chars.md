``` r
library(charcuterie)
#> 
#> Attaching package: 'charcuterie'
#> The following objects are masked from 'package:base':
#> 
#>     intersect, setdiff, union

chars("string")
#> [1] "string"
unclass(chars("string"))
#> [1] "s" "t" "r" "i" "n" "g"
string(chars("string"))
#> [1] "string"

string(chars("string"), collapse = "|")
#> [1] "s|t|r|i|n|g"

chars("string")[3]
#> [1] "r"
chars("banana")[seq(2, 6, 2)]
#> [1] "aaa"

head(chars("string"), 3)
#> [1] "str"
tail(chars("string"), 3)
#> [1] "ing"

word <- chars("string")
word[3] <- "R"
word
#> [1] "stRing"

table(chars("mississippi"))
#> 
#> i m p s 
#> 4 1 2 4

sort(chars("string"))
#> [1] "ginrst"
sort(chars("string"), decreasing = TRUE)
#> [1] "tsrnig"

rev(chars("string"))
#> [1] "gnirts"

length(chars("string")) == nchar("string")
#> [1] TRUE

"i" %in% chars("rhythm")
#> [1] FALSE
"y" %in% chars("rhythm")
#> [1] TRUE

is.element("y", chars("rhythm"))
#> [1] TRUE

c(chars("butter"), chars("fly"))
#> [1] "butterfly"

setdiff(chars("javascript"), chars("script"))
#> [1] "jav"
union(chars("bunny"), chars("rabbit"))
#> [1] "bunyrait"
intersect(chars("bob"), chars("rob"))
#> [1] "bo"
setequal(chars("stop"), chars("post"))
#> [1] TRUE
setequal(chars("stop"), chars("posit"))
#> [1] FALSE
unique(chars("mississippi"))
#> [1] "misp"

rev(toupper(chars("string")))
#> [1] "GNIRTS"

except(chars("javascript"), chars("script"))
#> [1] "java"
except(chars("carpet"), chars("car"))
#> [1] "pet"
```

<sup>Created on 2024-09-11 with [reprex v2.1.0](https://reprex.tidyverse.org)</sup>