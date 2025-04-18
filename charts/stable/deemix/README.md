# deemix

![Version: 1.1.2](https://img.shields.io/badge/Version-1.1.2-informational?style=flat-square) ![AppVersion: 2022.5.28-r206.a752a63e0e](https://img.shields.io/badge/AppVersion-2022.5.28--r206.a752a63e0e-informational?style=flat-square)

Deemix is a Deezer Download Manager

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/geek-cookbook/charts/issues/new/choose)**

## Source Code

* <https://gitlab.com/Bockiii/deemix-docker>
* <https://gitlab.com/RemixDev/deemix-gui>

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
helm install deemix geek-cookbook/deemix
```

## Installing the Chart

To install the chart with the release name `deemix`

```console
helm install deemix geek-cookbook/deemix
```

## Uninstalling the Chart

To uninstall the `deemix` deployment

```console
helm uninstall deemix
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install deemix \
  --set env.TZ="America/New York" \
    geek-cookbook/deemix
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install deemix geek-cookbook/deemix -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/geek-cookbook/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more environment variables in the [deemix-docker documentation](https://gitlab.com/Bockiii/deemix-docker). |
| env.PGID | string | `"1000"` | Group ID, see PUID |
| env.PUID | string | `"1000"` | User ID of the user you want the container to run as in order to fix folder permission issues |
| env.TZ | string | `"UTC"` | Set the container timezone |
| env.UMASK_SET | string | `"022"` | Default umask for downloaded files |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"registry.gitlab.com/bockiii/deemix-docker"` | image repository |
| image.tag | string | chart.appVersion | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

### Version 1.1.2

#### Added

N/A

#### Changed

* Upgraded `common` chart dependency to version 4.5.2

#### Fixed

N/A

### Older versions

A historical overview of changes can be found on [ArtifactHUB](https://artifacthub.io/packages/helm/geek-cookbook/deemix?modal=changelog)

## Support

- See the [Docs](https://geek-cookbook.funkypenguin.co.nz/)
- Open an [issue](https://github.com/geek-cookbook/charts/issues/new/choose)
- Ask a [question](https://github.com/geek-cookbook/organization/discussions)
- Join our [Discord](http://chat.funkypenguin.co.nz) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v0.1.1](https://github.com/geek-cookbook/helm-docs/releases/v0.1.1)
