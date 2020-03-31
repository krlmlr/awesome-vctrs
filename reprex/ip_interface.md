``` r
library(ipaddress)

ip_interface(c("192.168.0.1/10", "2001:db8:c3::abcd/45"))
#> <ip_interface[2]>
#> [1] 192.168.0.1/10       2001:db8:c3::abcd/45
ip_interface(ip_address(c("192.168.0.1", "2001:db8:c3::abcd")), c(10L, 45L))
#> <ip_interface[2]>
#> [1] 192.168.0.1/10       2001:db8:c3::abcd/45

as_ip_address(ip_interface("192.168.0.1/10"))
#> <ip_address[1]>
#> [1] 192.168.0.1
as_ip_network(ip_interface("192.168.0.1/10"))
#> <ip_network[1]>
#> [1] 192.128.0.0/10

ip_interface(NA)
#> <ip_interface[1]>
#> [1] <NA>
```

<sup>Created on 2020-03-31 by the [reprex package](https://reprex.tidyverse.org) (v0.3.0)</sup>
