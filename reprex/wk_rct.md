``` r
library(wk)

(x <- rct(1, 2, 3, 4))
#> <wk_rct[1]>
#> [1] [1 2 3 4]

# under the hood this is list(xmin, ymin, xmax, ymax)
unclass(x)
#> $xmin
#> [1] 1
#>
#> $ymin
#> [1] 2
#>
#> $xmax
#> [1] 3
#>
#> $ymax
#> [1] 4

# ...with basic methods for sf and wk
sf::st_as_sfc(x)
#> Geometry set for 1 feature
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: 1 ymin: 2 xmax: 3 ymax: 4
#> CRS:           NA
#> POLYGON ((1 2, 3 2, 3 4, 1 4, 1 2))
sf::st_bbox(x)
#> xmin ymin xmax ymax
#>    1    2    3    4
as_wkb(x)
#> <wk_wkb[1]>
#> [1] <POLYGON ((1 2, 3 2, 3 4, 1 4, 1 2))>
as_wkt(x)
#> <wk_wkt[1]>
#> [1] POLYGON ((1 2, 3 2, 3 4, 1 4, 1 2))

# you can attach a CRS object as well
rct(1, 2, 3, 4, crs = wk_crs_longlat())
#> <wk_rct[1] with CRS=OGC:CRS84>
#> [1] [1 2 3 4]

# ...and a wk_handle() method that powers a bunch of operations
wk_handle(x, wkt_writer())
#> <wk_wkt[1]>
#> [1] POLYGON ((1 2, 3 2, 3 4, 1 4, 1 2))

# you can create rct() vectors using rct(xmin, ymin, xmax, ymax)
# wk_bbox(), and wk_envelope()
wk_bbox(xy(1:5, 1:5))
#> <wk_rct[1]>
#> [1] [1 1 5 5]
wk_envelope(wk_linestring(xy(1:5, 1:5), c(rep(1, 3), rep(2, 2))))
#> <wk_rct[2]>
#> [1] [1 1 3 3] [4 4 5 5]
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>