``` r
library(palettes)

# Note: The bullet points preceding each colour hex code below will be
# appropriately coloured in the R console and in outputs that support ANSI
# colours.

# Colours can be specified by name (as listed by `grDevices::colours()`).
pal_colour("red")
#> <palettes_colour[1]>
#> • #FF0000

# Or by hex code:
pal_colour("#FF0000")
#> <palettes_colour[1]>
#> • #FF0000

# Multiple colours can be specified at once as a character vector:
pal_colour(c("#FF0000", "blue", "green"))
#> <palettes_colour[3]>
#> • #FF0000
#> • #0000FF
#> • #00FF00

# Named colour palettes can be specified in the same way:
pal_palette(
  palette_1 = c("#FF0000", "blue", "green"),
  palette_2 = c(c("yellow", "orange", "purple"))
)
#> <palettes_palette[2]>
#> $palette_1
#> <palettes_colour[3]>
#> • #FF0000
#> • #0000FF
#> • #00FF00
#> 
#> $palette_2
#> <palettes_colour[3]>
#> • #FFFF00
#> • #FFA500
#> • #A020F0
```

<sup>Created on 2022-11-25 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>
