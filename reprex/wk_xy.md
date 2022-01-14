``` r
library(wk)

(x <- xy(1:3, 4:6))
#> <wk_xy[3]>
#> [1] (1 4) (2 5) (3 6)

# under the hood this is list(x, y)
unclass(x)
#> $x
#> [1] 1 2 3
#>
#> $y
#> [1] 4 5 6

# ...with basic methods for sf and wk
sf::st_as_sfc(x)
#> Geometry set for 3 features
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 1 ymin: 4 xmax: 3 ymax: 6
#> CRS:           NA
#> POINT (1 4)
#> POINT (2 5)
#> POINT (3 6)
as_wkb(x)
#> <wk_wkb[3]>
#> [1] <POINT (1 4)> <POINT (2 5)> <POINT (3 6)>
as_wkt(x)
#> <wk_wkt[3]>
#> [1] POINT (1 4) POINT (2 5) POINT (3 6)

# you can attach a CRS object as well
xy(0, 1, crs = wk_crs_longlat())
#> <wk_xy[1] with CRS=OGC:CRS84>
#> [1] (0 1)

# other dimensions are supported too
xyz(0, 1, 2)
#> <wk_xyz[1]>
#> [1] Z (0 1 2)
xym(0, 1, 3)
#> <wk_xym[1]>
#> [1] M (0 1 3)
xyzm(0, 1, 2, 3)
#> <wk_xyzm[1]>
#> [1] ZM (0 1 2 3)

# ...and a wk_handle() method that powers a bunch of operations
wk_handle(x, wkt_writer())
#> <wk_wkt[3]>
#> [1] POINT (1 4) POINT (2 5) POINT (3 6)

# you can create xy() vectors using xy(x, y)
# as_xy(), and wk_handle(some_object, xy_writer())
wk_handle(wkt("POINT (0 1)"), xy_writer())
#> <wk_xy[1]>
#> [1] (0 1)
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>