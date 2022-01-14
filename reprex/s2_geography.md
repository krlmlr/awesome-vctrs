``` r
library(s2)

(x <- as_s2_geography("POINT (0 1)"))
#> <s2_geography[1]>
#> [1] <POINT (0 1)>

# under the hood this is a list() of external pointers
unclass(x)
#> [[1]]
#> <pointer: 0x12be1e650>

# ...with basic methods for sf and wk
sf::st_as_sfc(x)
#> Geometry set for 1 feature
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 0 ymin: 1 xmax: 0 ymax: 1
#> Geodetic CRS:  WGS 84
#> POINT (0 1)
wk::as_wkb(x)
#> <geodesic wk_wkb[1] with CRS=OGC:CRS84>
#> [1] <POINT (0 1)>
wk::as_wkt(x)
#> <geodesic wk_wkt[1] with CRS=OGC:CRS84>
#> [1] POINT (0 1)

# you can create s2_gepgraphy objects using as_s2_geography(),
# s2_geog_point(), s2_geog_from_text(), and s2_geog_from_wkb().
s2_geog_point(0, 1)
#> <s2_geography[1]>
#> [1] <POINT (0 1)>
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>