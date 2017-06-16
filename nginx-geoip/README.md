Nginx with GeoIP module
=======================

Nginx version: 1.13.1

Nginx modules:
You can check the Dockerfile for other enabled modules.

GeoIP databases can be found in: `/usr/share/GeoIP`

An `nginx.conf` is included as a starting point. You can map it against the
default configuration with the `-v` flag.

Resources:

- [Nginx GeoIP module documentation][1]
- [Building an in-house analytics collector with nginx][2]


[1]: http://nginx.org/en/docs/http/ngx_http_geoip_module.html
[2]: https://developer.rackspace.com/blog/building-an-in-house-analytics-collector-with-nginx/
