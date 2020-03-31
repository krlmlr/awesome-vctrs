``` r
library(ipaddress)

ip_address(c("192.168.0.1", "2001:db8::8a2e:370:7334"))
#> <ip_address[2]>
#> [1] 192.168.0.1             2001:db8::8a2e:370:7334
ip_address(c("255.255.255.255", "255.255.255.256"))
#> Warning: Invalid value on row 2: 255.255.255.256
#> <ip_address[2]>
#> [1] 255.255.255.255 <NA>

is_ipv6(ip_address("192.168.0.1"))
#> [1] FALSE
ip_address("192.168.0.1") & ip_address("255.192.0.0")
#> <ip_address[1]>
#> [1] 192.128.0.0
ip_address("192.168.0.1") + -1:1
#> <ip_address[3]>
#> [1] 192.168.0.0 192.168.0.1 192.168.0.2

ip_address(NA)
#> <ip_address[1]>
#> [1] <NA>
```

<sup>Created on 2020-03-31 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
