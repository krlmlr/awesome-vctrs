``` r
library(ipaddress)

ip_network(c("192.168.0.0/24", "2001:db8::/48"))
#> <ip_network[2]>
#> [1] 192.168.0.0/24 2001:db8::/48
ip_network(ip_address(c("192.168.0.0", "2001:db8::")), c(24L, 48L))
#> <ip_network[2]>
#> [1] 192.168.0.0/24 2001:db8::/48
ip_network(c("192.168.0.0/32", "192.168.0.0/33"))
#> Warning: Invalid value on row 2: 192.168.0.0/33
#> <ip_network[2]>
#> [1] 192.168.0.0/32 <NA>

ip_network("192.168.0.1/24")
#> Warning: Invalid value on row 1: 192.168.0.1/24 (host bits set)
#> <ip_network[1]>
#> [1] <NA>
ip_network("192.168.0.1/24", strict = FALSE)
#> <ip_network[1]>
#> [1] 192.168.0.0/24

is_ipv6(ip_network("192.168.0.0/24"))
#> [1] FALSE
prefix_length(ip_network("192.168.0.0/24"))
#> [1] 24
network_address(ip_network("192.168.0.0/24"))
#> <ip_address[1]>
#> [1] 192.168.0.0
broadcast_address(ip_network("192.168.0.0/24"))
#> <ip_address[1]>
#> [1] 192.168.0.255

ip_network(NA)
#> <ip_network[1]>
#> [1] <NA>
```

<sup>Created on 2020-03-31 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
