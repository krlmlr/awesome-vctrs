``` r
library(geos)

(x <- as_geos_geometry("POINT (0 1)"))
#> <geos_geometry[1]>
#> [1] <POINT (0 1)>

# under the hood this is a list() of external pointers to GEOSGeometry
unclass(x)
#> [[1]]
#> <pointer: 0x12e087020>

# ...with basic methods for sf
sf::st_as_sfc(x)
#> Geometry set for 1 feature
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 0 ymin: 1 xmax: 0 ymax: 1
#> CRS:           NA
#> POINT (0 1)

# ...and a wk_handle() method that powers a bunch of operations
wk::wk_handle(x, wk::xy_writer())
#> <wk_xy[1]>
#> [1] (0 1)

# you can assign a CRS and/or mark edges as geodesic
geos_read_wkt("POINT (0 1)", crs = wk::wk_crs_longlat())
#> <geos_geometry[1] with CRS=OGC:CRS84>
#> [1] <POINT (0 1)>

# you can create geos_geometry() vectors using
# as_geos_geometry(), geos_read_wkt(), geos_read_wkb(),
# geos_read_geojson(), and wk_handle(some_object, geos_geometry_writer())
wk::wk_handle(wk::xy(0, 1), geos_geometry_writer())
#> <geos_geometry[1]>
#> [1] <POINT (0 1)>
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>