# IP addresses in Dhall

Correct by construction IPv4 and IPv6 addresses in Dhall.

The implementation is slow and horrible but this shows that it can be done.

## IPv4

```dhall
let IPv4 = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv4/IPv4
let IPv4/build = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv4/build
let IPv4/show = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv4/show
let ip : IPv4 = IPv4/build 127 0 0 1
in IPv4/show ip
```

`"127.0.0.1"`

## IPv6

```dhall
let IPv6 = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv6/IPv6
let IPv6/build = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv6/build
let IPv6/show = https://raw.githubusercontent.com/duairc/dhall-ip-address/master/IPv6/show
-- Dhall lacks hexadecimal literals so the following will have to suffice
let a = 10
let b = 11
let c = 12
let d = 13
let e = 14
let f = 15
let ip : IPv6 = IPv6/build 2 0 0 1  0 d b 8  a c 1 0  f e 0 1  0 0 0 0  0 0 0 0  0 0 0 0  0 0 0 0
in IPv6/show ip
```

`"2001:db8:ac10:fe01::"`
