# lazylibrarian

This is a helm chart for [lazylibrarian](https://gitlab.com/LazyLibrarian/LazyLibrarian) leveraging the [Linuxserver.io image](https://hub.docker.com/r/linuxserver/lazylibrarian/)

## TL;DR

```shell
$ helm repo add k8s-usenet https://raw.githubusercontent.com/aldoborrero/k8s-usenet/master/charts/
$ helm install k8s-usenet/lazylibrarian
```

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm install my-release k8s-usenet/lazylibrarian
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following tables lists the configurable parameters of the Sentry chart and their default values.

| Parameter                              | Description                                                                                         | Default                     |
| -------------------------------------- | --------------------------------------------------------------------------------------------------- | --------------------------- |
| `image.repository`                     | Image repository                                                                                    | `linuxserver/lazylibrarian` |
| `image.tag`                            | Image tag. Possible values listed [here](https://hub.docker.com/r/linuxserver/lazylibrarian/tags/). | `amd64-latest`              |
| `image.pullPolicy`                     | Image pull policy                                                                                   | `Always`                    |
| `strategyType`                         | Specifies the strategy used to replace old Pods by new ones                                         | `Recreate`                  |
| `timezone`                             | Timezone the lazylibrarian instance should run as, e.g. 'America/New_York'                          | `UTC`                       |
| `puid`                                 | process userID the lazylibrarian instance should run as                                             | `1001`                      |
| `pgid`                                 | process groupID the lazylibrarian instance should run as                                            | `1001`                      |
| `service.type`                         | Kubernetes service type for the lazylibrarian GUI                                                   | `ClusterIP`                 |
| `service.port`                         | Kubernetes port where the lazylibrarian GUI is exposed                                              | `5299`                      |
| `service.annotations`                  | Service annotations for the lazylibrarian GUI                                                       | `{}`                        |
| `service.labels`                       | Custom labels                                                                                       | `{}`                        |
| `service.loadBalancerIP`               | Loadbalance IP for the lazylibrarian GUI                                                            | `{}`                        |
| `service.loadBalancerSourceRanges`     | List of IP CIDRs allowed access to load balancer (if supported)                                     | None                        |
| `ingress.enabled`                      | Enables Ingress                                                                                     | `false`                     |
| `ingress.annotations`                  | Ingress annotations                                                                                 | `{}`                        |
| `ingress.labels`                       | Custom labels                                                                                       | `{}`                        |
| `ingress.path`                         | Ingress path                                                                                        | `/`                         |
| `ingress.hosts`                        | Ingress accepted hostnames                                                                          | `chart-example.local`       |
| `ingress.tls`                          | Ingress TLS configuration                                                                           | `[]`                        |
| `persistence.config.enabled`           | Use persistent volume to store configuration data                                                   | `true`                      |
| `persistence.config.size`              | Size of persistent volume claim                                                                     | `1Gi`                       |
| `persistence.config.existingClaim`     | Use an existing PVC to persist data                                                                 | `nil`                       |
| `persistence.config.storageClass`      | Type of persistent volume claim                                                                     | `-`                         |
| `persistence.config.accessMode`        | Persistence access mode                                                                             | `ReadWriteOnce`             |
| `persistence.downloads.enabled`        | Use persistent volume for downloads                                                                 | `true`                      |
| `persistence.downloads.size`           | Size of persistent volume claim                                                                     | `10Gi`                      |
| `persistence.downloads.existingClaim`  | Use an existing PVC to persist data                                                                 | `nil`                       |
| `persistence.downloads.storageClass`   | Type of persistent volume claim                                                                     | `-`                         |
| `persistence.downloads.accessMode`     | Persistence access mode                                                                             | `ReadWriteOnce`             |
| `persistence.books.enabled`            | Use persistent volume for books persistence                                                         | `true`                      |
| `persistence.books.size`               | Size of persistent volume claim                                                                     | `10Gi`                      |
| `persistence.books.existingClaim`      | Use an existing PVC to persist data                                                                 | `nil`                       |
| `persistence.books.storageClass`       | Type of persistent volume claim                                                                     | `-`                         |
| `persistence.books.accessMode`         | Persistence access mode                                                                             | `ReadWriteOnce`             |
| `persistence.extraExistingClaimMounts` | Optionally add multiple existing claims                                                             | `[]`                        |
| `resources`                            | CPU/Memory resource requests/limits                                                                 | `{}`                        |
| `nodeSelector`                         | Node labels for pod assignment                                                                      | `{}`                        |
| `tolerations`                          | Toleration labels for pod assignment                                                                | `[]`                        |
| `affinity`                             | Affinity settings for pod assignment                                                                | `{}`                        |
| `podAnnotations`                       | Key-value pairs to add as pod annotations                                                           | `{}`                        |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
helm install my-release \
  --set timezone="America/New York" \
    k8s-usenet/lazylibrarian
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
helm install my-release -f values.yaml k8s-usenet/lazylibrarian
```

Read through the [values.yaml](values.yaml) file. It has several commented out suggested values.
