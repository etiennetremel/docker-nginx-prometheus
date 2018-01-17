Alpine NGINX with Prometheus metrics
====================================

> Slim Docker image with NGINX and Prometheus to serve metrics

![Docker build status][badge-build-status] ![Image size][badge-image-size]

[badge-build-status]: https://img.shields.io/docker/build/etiennetremel/nginx-prometheus.svg
[badge-image-size]: https://img.shields.io/imagelayers/image-size/etiennetremel/nginx-prometheus/latest.svg

## Getting started

### Build

```
$ docker build -t etiennetremel/nginx-prometheus .
```

### Run

```
$ docker run -ti -p 80:80 -p 9101:9101 etiennetremel/nginx-prometheus
```

### Test

```
$ curl localhost:9101
```

## Provided metrics

```
# HELP nginx_http_request_duration_seconds HTTP request latency
# TYPE nginx_http_request_duration_seconds histogram
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.005"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.010"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.020"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.030"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.050"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.075"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.100"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.200"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.300"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.400"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.500"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="00.750"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="01.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="01.500"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="02.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="03.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="04.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="05.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="10.000"} 2
nginx_http_request_duration_seconds_bucket{host="localhost",le="+Inf"} 2
nginx_http_request_duration_seconds_count{host="localhost"} 2
nginx_http_request_duration_seconds_sum{host="localhost"} 0
# HELP nginx_http_requests_total Number of HTTP requests
# TYPE nginx_http_requests_total counter
nginx_http_requests_total{host="localhost",status="200"} 1
nginx_http_requests_total{host="localhost",status="404"} 1
# HELP nginx_metric_errors_total Number of nginx-lua-prometheus errors
# TYPE nginx_metric_errors_total counter
nginx_metric_errors_total 0
```

## References

This image is based on the following repositories:

- [Docker Nginx](https://github.com/nginxinc/docker-nginx)
- [Nginx development kit](https://github.com/simpl/ngx_devel_kit)
- [Nginx Lua module](https://github.com/openresty/lua-nginx-module)
- [Nginx Lua Prometheus](https://github.com/knyar/nginx-lua-prometheus)
