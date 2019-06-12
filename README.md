# PGBouncer Helm Chart

This is an implementation of PGBouncer found here:

 * https://github.com/aerospike/aerospike-kubernetes

## Pre Requisites:

* Kubernetes 1.7+ with beta APIs enabled and support for statefulsets

* Requires at least `v2.5.0` version of helm to support

## Chart Details

This chart will do the following:

* Connection pooling on top of a Postgres Instance
* Expose Prometheus metrics endpoint

### Installing the Chart

To install the chart with the release name `bouncer` using a dedicated namespace(recommended):

```
$ helm package pgbouncer
$ helm install -n bouncer pgbouncer-0.0.6.tgz
```

The chart can be customized using the following configurable parameters:

| Parameter                       | Description                                                     |
| ------------------------------- | ----------------------------------------------------------------|
| `image.repository`              | PGBouncer Container image name                                  |
| `image.tag`                     | PGBouncer Container image tag                                   |
| `image.pullPolicy`              | PGBouncer Container pull policy                                 |
| `pgbouncer`                     | Custom PGBouncer configuration                                  |
| `exporter`                      | Prometheus exporter configuration                               |
| `resources`                     | resource requests and limits                                    |
| `nodeSelector`                  | Labels for pod assignment                                       |

Specify parameters using `--set key=value[,key=value]` argument to `helm install`

