# Adminer

* Installs [Adminer](https://www.adminer.org)

## TL;DR;

```console
$ helm repo add mogaal https://mogaal.github.io/helm-charts/
$ helm install mogaal/adminer
```

## Introduction

This chart bootstraps a [adminer](https://www.adminer.org) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

## Installing the Chart

To install the chart with the release name `my-release`:

```console
$ $ helm repo add mogaal https://mogaal.github.io/helm-charts/
$ helm install --name my-release mogaal/adminer
```

The command deploys ADminer on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
$ helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the YACE Exporter chart and their default values.

| Parameter                         | Description                                                             | Default                     |
| --------------------------------- | ----------------------------------------------------------------------- | --------------------------- |
| `image.repository`                | Image                                                                   | `adminer`                   |
| `image.tag`                       | Image tag                                                               | `standalone`                |
| `image.pullPolicy`                | Image pull policy                                                       | `IfNotPresent`              |
| `command`                         | Container entrypoint command                                            | `[]`                        |
| `service.type`                    | Service type                                                            | `ClusterIP`                 |
| `service.port`                    | The service port                                                        | `80`                        |
| `service.annotations`             | Custom annotations for service                                          | `{}`                        |
| `service.labels`                  | Additional custom labels for the service                                | `{}`                        |
| `resources`                       |                                                                         | `{}`                        |
| `config`                          | YACE configuration (default found in the webpage)                       | `example configuration`     |
| `rbac.create`                     | If true, create & use RBAC resources                                    | `false`                     |
| `tolerations`                     | Add tolerations                                                         | `[]`                        |
| `nodeSelector`                    | node labels for pod assignment                                          | `{}`                        |
| `affinity`                        | node/pod affinities                                                     | `{}`                        |
| `livenessProbe`                   | Liveness probe settings                                                 |                             |
| `readinessProbe`                  | Readiness probe settings                                                |                             |
| `ingress.enabled`                 | Enables Ingress                                                         | `false`                     |
| `ingress.annotations`             | Ingress annotations                                                     | `{}`                        |
| `ingress.labels`                  | Custom labels                                                           | `{}`                        |
| `ingress.hosts`                   | Ingress accepted hostnames                                              | `[]`                        |
| `ingress.tls`                     | Ingress TLS configuration                                               | `[]`                        |

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```console
$ helm install --name my-release \
    --set image.repository=adminer-01 \
    mogaal/adminer
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart. For example,

```console
$ helm install --name my-release -f values.yaml mogaal/adminer
```
