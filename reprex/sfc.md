``` r
library(sf)
#> Linking to GEOS 3.9.1, GDAL 3.2.3, PROJ 7.2.1

(x <- st_sfc(st_point(c(0, 1))))
#> Geometry set for 1 feature
#> Geometry type: POINT
#> Dimension:     XY
#> Bounding box:  xmin: 0 ymin: 1 xmax: 0 ymax: 1
#> CRS:           NA
#> POINT (0 1)

# under the hood this is a list() of 'sfg' objects (e.g., st_point())
# with a cached bounding box, CRS, empty count and precision
unclass(x)
#> [[1]]
#> POINT (0 1)
#>
#> attr(,"precision")
#> [1] 0
#> attr(,"bbox")
#> xmin ymin xmax ymax
#>    0    1    0    1
#> attr(,"crs")
#> Coordinate Reference System: NA
#> attr(,"n_empty")
#> [1] 0

# Typically sfc objects are created as part of an 'sf' object,
# which is a data.frame with an 'sfc' column. These can be created
# using read_sf() from most spatial vector files:
df <- read_sf(system.file("shape/nc.shp", package = "sf"))
st_geometry(df)
#> Geometry set for 100 features
#> Geometry type: MULTIPOLYGON
#> Dimension:     XY
#> Bounding box:  xmin: -84.32385 ymin: 33.88199 xmax: -75.45698 ymax: 36.58965
#> Geodetic CRS:  NAD27
#> First 5 geometries:
#> MULTIPOLYGON (((-81.47276 36.23436, -81.54084 3...
#> MULTIPOLYGON (((-81.23989 36.36536, -81.24069 3...
#> MULTIPOLYGON (((-80.45634 36.24256, -80.47639 3...
#> MULTIPOLYGON (((-76.00897 36.3196, -76.01735 36...
#> MULTIPOLYGON (((-77.21767 36.24098, -77.23461 3...
```

<sup>Created on 2022-01-13 by the [reprex package](https://reprex.tidyverse.org) (v2.0.1)</sup>