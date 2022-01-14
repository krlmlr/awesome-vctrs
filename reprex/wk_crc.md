``` r
library(wk)

(x <- crc(1, 2, r = 0.5))
#> <wk_crc[1]>
#> [1] [1 2, r = 0.5]

# under the hood this is list(x, y, radius)
unclass(x)
#> $x
#> [1] 1
#>
#> $y
#> [1] 2
#>
#> $r
#> [1] 0.5

# ...with basic methods for sf and wk
sf::st_as_sfc(x)
#> Geometry set for 1 feature
#> Geometry type: POLYGON
#> Dimension:     XY
#> Bounding box:  xmin: 0.5 ymin: 1.5 xmax: 1.5 ymax: 2.5
#> CRS:           NA
#> POLYGON ((1.5 2, 1.499013 2.031395, 1.496057 2....
sf::st_bbox(x)
#> xmin ymin xmax ymax
#>  0.5  1.5  1.5  2.5
as_wkb(x)
#> <wk_wkb[1]>
#> [1] <POLYGON ((1.5 2, 1.499013 2.031395, 1.496057 2.062667, 1.491144 2.093691, 1.484292 2.124345, 1.475528 2.154508...>
as_wkt(x)
#> <wk_wkt[1]>
#> [1] POLYGON ((1.5 2, 1.499013 2.031395, 1.496057 2.062667, 1.491144 2.093691, 1.484292 2.124345, 1.475528 2.154508...

# you can attach a CRS object as well
crc(1, 2, r = 0.5, crs = wk_crs_longlat())
#> <wk_crc[1] with CRS=OGC:CRS84>
#> [1] [1 2, r = 0.5]

# ...and a wk_handle() method that powers a bunch of operations
wk_handle(x, wkt_writer())
#> <wk_wkt[1]>
#> [1] POLYGON ((1.5 2, 1.499013 2.031395, 1.496057 2.062667, 1.491144 2.093691, 1.484292 2.124345, 1.475528 2.154508...

# you can control the point density used to convert to a polygon
wk_handle(x, wkt_writer(), resolution = 0.8)
#> <wk_wkt[1]>
#> [1] POLYGON ((1.5 2, 1 2.5, 0.5 2, 1 1.5, 1.5 2))

# you can create crc() vectors using crc(x, y, radius)
# and using a few geos functions that return circles
geos::geos_minimum_bounding_crc("LINESTRING (0 0, 1 1)")
#> <wk_crc[1]>
#> [1] [0.5 0.5, r = 0.7071068]
geos::geos_maximum_inscribed_crc("POLYGON ((0 0, 0 1, 1 0, 0 0))", 0.01)
#> <wk_crc[1]>
#> [1] [0.2929688 0.2929688, r = 0.2927864]
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>