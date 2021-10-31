``` r
library("nombre")

nom_card(2)
#> [1] "two"
nom_card(8^(1:10))
#>  [1] "eight"                                                                                       
#>  [2] "sixty-four"                                                                                  
#>  [3] "five hundred twelve"                                                                         
#>  [4] "four thousand ninety-six"                                                                    
#>  [5] "thirty-two thousand seven hundred sixty-eight"                                               
#>  [6] "two hundred sixty-two thousand one hundred forty-four"                                       
#>  [7] "two million ninety-seven thousand one hundred fifty-two"                                     
#>  [8] "sixteen million seven hundred seventy-seven thousand two hundred sixteen"                    
#>  [9] "one hundred thirty-four million two hundred seventeen thousand seven hundred twenty-eight"   
#> [10] "one billion seventy-three million seven hundred forty-one thousand eight hundred twenty-four"

nom_card(2) + 0.75
#> [1] "two and three quarters"
nom_card(2) * -4
#> [1] "negative eight"
sqrt(nom_card(2, max_denom = 100))
#> [1] "one and twenty-nine seventieths"

nom_ord(1:5)
#> [1] "first"  "second" "third"  "fourth" "fifth"
nom_adv(1:5)
#> [1] "once"        "twice"       "three times" "four times"  "five times"
nom_coll(1:5)
#> [1] "the"       "both"      "all three" "all four"  "all five"

uncardinal(c("two", "negative eight", "infinity"))
#> [1]   2  -8 Inf

nom_card(2) < 3
#> [1] TRUE
nom_card(2) == 2
#> [1] TRUE
nom_card(2) == "two"
#> [1] TRUE

nom_ord(2) == 2
#> [1] TRUE
nom_ord(2) == "second"
#> [1] TRUE
```

<sup>Created on 2021-10-31 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
