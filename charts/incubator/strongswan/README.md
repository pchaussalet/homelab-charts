# strongswan

![Version: 0.3.2](https://img.shields.io/badge/Version-0.3.2-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

strongSwan – the OpenSource IPsec-based VPN Solution

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://github.com/reitermarkus/strongswan>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.5.2 |

## TL;DR

```console
helm repo add geek-cookbook https://geek-cookbook.github.io/charts/
helm repo update
helm install strongswan geek-cookbook/strongswan
```

## Installing the Chart

To install the chart with the release name `strongswan`

```console
helm install strongswan geek-cookbook/strongswan
```

## Uninstalling the Chart

To uninstall the `strongswan` deployment

```console
helm uninstall strongswan
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install strongswan \
  --set env.TZ="America/New York" \
    geek-cookbook/strongswan
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install strongswan geek-cookbook/strongswan -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| dnsPolicy | string | `"ClusterFirstWithHostNet"` |  |
| env | object | See below | environment variables. See more environment variables in the [strongswan documentation](https://github.com/reitermarkus/strongswan). |
| env.TZ | string | `"UTC"` | Set the container timezone |
| hostNetwork | bool | `true` |  |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"ghcr.io/reitermarkus/strongswan"` | image repository |
| image.tag | string | `"v1.0.0"` | image tag |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| probes | object | See values.yaml | Configures the probes for the main Pod. |
| securityContext | object | See values.yaml | Security contexts required for container. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 0.3.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/strongswan?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
