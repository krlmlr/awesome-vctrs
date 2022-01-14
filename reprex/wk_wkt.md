``` r
library(wk)

(x <- wkt("POINT (0 1)"))
#> <wk_wkt[1]>
#> [1] POINT (0 1)

# under the hood this is just a character()
unclass(x)
#> [1] "POINT (0 1)"

# ...with basic methods for sf
sf::st_as_sfc(x)
#> Geometry set for 1 feature
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 0 ymin: 1 xmax: 0 ymax: 1
#> CRS:           NA
#> POINT (0 1)
sf::st_geometry(x)
#> Geometry set for 1 feature
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 0 ymin: 1 xmax: 0 ymax: 1
#> CRS:           NA
#> POINT (0 1)
sf::st_bbox(x)
#> xmin ymin xmax ymax
#>    0    1    0    1

# ...and a wk_handle() method that powers a bunch of operations
wk_handle(x, xy_writer())
#> <wk_xy[1]>
#> [1] (0 1)

# you can assign a CRS and/or mark edges as geodesic
wkt(x, crs = wk_crs_longlat(), geodesic = TRUE)
#> <geodesic wk_wkt[1] with CRS=OGC:CRS84>
#> [1] POINT (0 1)

# you can create wkb() vectors using wkt(<character>),
# as_wkt(), and wk_handle(some_object, wkt_writer())
wk_handle(xy(0, 1), wkt_writer())
#> <wk_wkt[1]>
#> [1] POINT (0 1)
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>