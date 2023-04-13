# Awesome VectoRs

A curated list of amazingly awesome R vector classes, and the packages that provide them.


## Contributing

Please read [CONTRIBUTING](./CONTRIBUTING.md) if you wish to add a new vector class.


## Table of Contents

- [Awesome VectoRs](#awesome-vectors)
  - [Contributing](#contributing)
  - [Table of Contents](#table-of-contents)
  - [Base](#base)
    - [base](#base-1)
  - [Numbers](#numbers)
    - [bignum](#bignum)
  - [Date and time](#date-and-time)
  - [Strings](#strings)
  - [Compound](#compound)
  - [Computing](#computing)
  - [Geospatial](#geospatial)
  - [Internal](#internal)
  - [Colours](#colours)
- [Resources](#resources)
  - [Books](#books)
  - [Repositories](#repositories)
  - [Blog posts](#blog-posts)
  - [Talks](#talks)
  - [License](#license)


## Base

*Classes provided by base R.*

### base

* [`character`](https://rdrr.io/r/base/character.html) - Strings: [`"a"`](reprex/character.md)
* [`POSIXct`](https://rdrr.io/r/base/as.POSIXlt.html) - Calendar time with time zone, stored as days since epoch: [`2020-03-03 09:16:17 CET`](reprex/POSIXct.md)
* [`POSIXlt`](https://rdrr.io/r/base/as.POSIXlt.html) - Calendar time with time zone, stored as record of components: [`2020-03-03 09:16:17 CET`](reprex/POSIXlt.md)


## Numbers

*Classes that wrap numbers.*

### [base](https://rdrr.io/r/base/)

* [`hexmode`](https://rdrr.io/r/base/hexmode.html) - Hexadecimal numbers: [`2A`](reprex/hexmode.md)
* [`integer`](https://rdrr.io/r/base/integer.html) - 32-bit integers: [`1`](reprex/integer.md)
* [`numeric`](https://rdrr.io/r/base/numeric.html) - Floating-point numbers: [`1.234567`](reprex/numeric.md)
* [`numeric_version`](https://rdrr.io/r/base/numeric_version.html) - Software versions: [`'1.23.456'`](reprex/numeric_version.md)
* [`octmode`](https://rdrr.io/r/base/octmode.html) - Octal numbers: [`52`](reprex/octmode.md)

### [bignum](https://davidchall.github.io/bignum/)

* [`bigfloat`](https://davidchall.github.io/bignum/reference/bigfloat.html) - High precision numbers: [`0.33333333333333333333333333333333333333333333333333`](reprex/bigfloat.md)
* [`biginteger`](https://davidchall.github.io/bignum/reference/biginteger.html) - Arbitrary precision integers: [`25852016738884976640000`](reprex/biginteger.md)

### [debkeepr](https://jessesadler.github.io/debkeepr/)

* [`deb_decimal`](https://jessesadler.github.io/debkeepr/reference/deb_decimal.html) - Non-decimal currencies as `double` with `unit` and `bases` attributes: [`3.825`](reprex/deb_decimal.md)
* [`deb_lsd`](https://jessesadler.github.io/debkeepr/reference/deb_lsd.html) - Tripartite non-decimal currencies: [`8:13s:4d`](reprex.deb_lsd.md)
* [`deb_tetra`](https://jessesadler.github.io/debkeepr/reference/deb_tetra.html) - Tetrapartite non-decimal currencies: [`8:13s:4d:3f`](reprex.deb_tetra.md)

### [errors](https://r-quantities.github.io/errors/)

* [`errors`](https://r-quantities.github.io/errors/reference/errors.html) - Numbers with uncertainty: [`1 ± 0.3`](reprex/errors.md)

### [fracture](https://fracture.rossellhayes.com/)

* [`fracture`](https://fracture.rossellhayes.com/reference/fracture.html) - Fractions: [`1/3`](reprex/fracture.md)

### [nombre](https://nombre.rossellhayes.com/)

* [`nombre`](https://nombre.rossellhayes.com/) - Number names: [`one`](reprex/nombre.md)

### [pillar](https://pillar.r-lib.org/)

* [`num`](https://pillar.r-lib.org/reference/num) - Numbers with formatting: [`1.00`](reprex/num.md)

### [quantities](https://r-quantities.github.io/quantities/)

* [`quantities`](https://r-quantities.github.io/quantities/reference/quantities.html) - Numbers with units and uncertainty: [`1 ± 0.3 [m/s]`](reprex/quantities.md)

### [units](### [quantities](https://r-quantities.github.io/units/))

* [`units`](https://r-quantities.github.io/units/reference/set_units.html) - Numbers with units: [`1 [m/s]`](reprex/units.md)

## Date and time

*Classes that wrap dates and times.*

* [`aweek`](https://www.repidemicsconsortium.org/aweek) - Weeks that start on any day of the week: [`2020-W10-2`](reprex/aweek.md)
* [`calendar`](https://clock.r-lib.org/reference/year_month_day.html) - Alternative representations of calendar dates, such as year-quarter-day or year-month-weekday: [`2019-02-Sun[2]`](reprex/calendar.md)
* [`date_y`, `date_yq`, `date_ym`, `date_yw`](https://s-fleck.github.io/dint/reference/date_y.html) - Years, year-quarter, year-month and year-week: [`2020-Q1`](reprex/date_xx.md)
* [`hms`](https://hms.tidyverse.org/reference/hms.html) - Time of day: [`12:34:56`](reprex/hms.md)
* [`term`](https://github.com/ir-sfsu/intermittent) - Represent ordinal academic semesters: [`20164`](reprex/intermittent.md)
* [`time_point`](https://clock.r-lib.org/reference/index.html#section-time-points) - Variable precision points in time, with and without time zones: [`"2020-02-01 02:03:04.000005"`](reprex/time_point.md)
* [`yearquarter`, `yearmonth`, `yearweek`](https://tsibble.tidyverts.org/reference/year-month.html) - Year-quarter, year-month and year-week: [`2021 Oct`](reprex/yearxx.md)
* [`yr`](https://era.joeroe.io/reference/yr.html) - Year-based time scales: [`4.2 ka`](reprex/yr.md)

## Strings

*Classes that wrap character strings.*

* [`char`](https://pillar.r-lib.org/reference/char) - Strings with minimum width and custom abbreviation: [`abc…xyz`](reprex/char.md)

## Compound

*Classes that wrap complex objects.*

* [`blob`](https://blob.tidyverse.org/reference/blob.html) - Binary Large OBjects: [`blob[42 B]`](reprex/blob.md)
* [`doi`](https://subugoe.github.io/biblids/reference/doi.html) - Digital Object Identifiers (DOIs): [`10.1000/1`](reprex/doi.md)
* [`intrval`](https://github.com/psolymos/intrval) - Relational operators for intervals: [`x %[]% c(a, b)`](reprex/intrval.md)
* [`iv`](https://davisvaughan.github.io/ivs/) - Interval vectors: [`[2019-01-05, 2019-05-06) [2019-01-06, 2019-05-22)`](reprex/iv.md)
* [`labelled`](https://haven.tidyverse.org/reference/labelled.html) - Labelled vectors: [`<Labelled double> 3` with labels](reprex/labelled.md)
* [`mixed_units`](https://r-quantities.github.io/units/reference/mixed_units.html) - Numbers with different units: [`1 [m], 2 [kg]`](reprex/mixed_units.md)
* [`phone`](https://socialresearchcentre.github.io/dialr/reference/dialr-phone.html) - Phone numbers parsed with Google's [libphonenumber](https://github.com/google/libphonenumber) for formatting and further processing: [`# Parsed phone numbers: 5 total, 4 successfully parsed`](reprex/phone.md)
* [`term`](https://poissonconsulting.github.io/term/) - Labels for values in numeric objects: [`beta[1,2]`](reprex/term.md)

## Computing

*Classes related to computing*

* [`ip_address`](https://davidchall.github.io/ipaddress/reference/ip_address.html) - IP address: [`192.168.0.1`](reprex/ip_address.md)
* [`ip_interface`](https://davidchall.github.io/ipaddress/reference/ip_interface.html) - IP interface: [`192.168.0.1/24`](reprex/ip_interface.md)
* [`ip_network`](https://davidchall.github.io/ipaddress/reference/ip_network.html) - IP network: [`192.168.0.0/24`](reprex/ip_network.md)

## Geospatial

*Classes related to geospatial*

- [`crc`](https://paleolimbot.github.io/wk/reference/crc.html) - Circle: [`[1 2, r = 0.5]`](reprex/wk_crc.md)
- [`geos_geometry`](https://paleolimbot.github.io/geos/reference/as_geos_geometry.html) - Geometry vector as GEOS external pointers: [`<POINT (0 1)>`](reprex/geos_geometry.md)
- [`rct`](https://paleolimbot.github.io/wk/reference/rct.html) - Rectangle:  [`[1 2 3 4]`](reprex/wk_rct.md)
- [`s2_geography`](https://r-spatial.github.io/s2/reference/as_s2_geography.html), [`s2_cell`](https://r-spatial.github.io/s2/reference/s2_cell.html) - Geometry vector of points on the sphere as external pointers to S2 objects, S2 cell IDs as 64-bit integers: [`<POINT (0 1)>`](reprex/s2_geography.md)
- [`sfc`](https://r-spatial.github.io/sf/reference/sfc.html) - Geometry vector in spatial data frames: [`POINT (0 1)`](reprex/sfc.md)
- [`wkb`](https://paleolimbot.github.io/wk/reference/wkb.html) - Well-known binary geometry: [`<POINT (0 1)>`](reprex/wk_wkb.md)
- [`wkt`](https://paleolimbot.github.io/wk/reference/wkt.html) - Well-known text geometry: [`POINT (0 1)`](reprex/wk_wkt.md)
- [`xy`](https://paleolimbot.github.io/wk/reference/xy.html) - Points:  [`(1 4)`](reprex/wk_xy.md)

## Internal

*Classes implemented by packages for their own use*

* [`tokenlist`](https://tidymodels.github.io/textrecipes/dev/articles/tokenlist.html) - List of tokens: [`[3 tokens]` with number of unique tokens](reprex/tokenlist.md)

## Colours

*Classes related to colours*

* [`palettes_colour`](https://mccarthy-m-g.github.io/palettes/reference/pal_colour.html) - Colours: $\color{red}{\bullet}$ [` #FF0000`](reprex/palettes.md)
* [`palettes_palette`](https://mccarthy-m-g.github.io/palettes/reference/pal_palette.html) - Colour palettes: $\color{red}{\bullet}$ [` #FF0000`](reprex/palettes.md)

# Resources

## Books

* [Advanced R](https://adv-r.hadley.nz/) by Hadley Wickham


## Repositories

* [vctrs](https://vctrs.r-lib.org/): simplifies creating vector classes


## Blog posts

* [Earo Wang: A practical guide to vctrs-powered S3 programming](https://blog.earo.me/2019/11/03/practical-guide-to-s3/): using vctrs for turtle graphics


## Talks

* [Jesse Sadler, vctrs: Creating custom vector classes with the vctrs package at RStudio::conf2020](https://resources.rstudio.com/rstudio-conf-2020/vctrs-creating-custom-vector-classes-with-the-vctrs-package-jesse-sadler) with the companion tutorial [debvctrs](https://github.com/jessesadler/debvctrs)


## License

![cc license](http://i.creativecommons.org/l/by-sa/4.0/88x31.png)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-sa/4.0/) license.
