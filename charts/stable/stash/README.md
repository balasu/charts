# stash

![Version: 3.0.1](https://img.shields.io/badge/Version-3.0.1-informational?style=flat-square) ![AppVersion: latest](https://img.shields.io/badge/AppVersion-latest-informational?style=flat-square)

An organizer for your porn, written in Go

**This chart is not maintained by the upstream project and any issues with the chart should be raised [here](https://github.com/k8s-at-home/charts/issues/new/choose)**

## Source Code

* <https://github.com/stashapp/stash>
* <https://hub.docker.com/r/stashapp/stash>

## Requirements

Kubernetes: `>=1.16.0-0`

## Dependencies

| Repository | Name | Version |
|------------|------|---------|
| https://library-charts.k8s-at-home.com | common | 4.0.1 |

## TL;DR

```console
helm repo add k8s-at-home https://k8s-at-home.com/charts/
helm repo update
helm install stash k8s-at-home/stash
```

## Installing the Chart

To install the chart with the release name `stash`

```console
helm install stash k8s-at-home/stash
```

## Uninstalling the Chart

To uninstall the `stash` deployment

```console
helm uninstall stash
```

The command removes all the Kubernetes components associated with the chart **including persistent volumes** and deletes the release.

## Configuration

Read through the [values.yaml](./values.yaml) file. It has several commented out suggested values.
Other values may be used from the [values.yaml](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml) from the [common library](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common).

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`.

```console
helm install stash \
  --set env.TZ="America/New York" \
    k8s-at-home/stash
```

Alternatively, a YAML file that specifies the values for the above parameters can be provided while installing the chart.

```console
helm install stash k8s-at-home/stash -f values.yaml
```

## Custom configuration

N/A

## Values

**Important**: When deploying an application Helm chart you can add more values from our common library chart [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common)

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| env | object | See below | environment variables. See more environment variables in the [stashapp documentation](https://raw.githubusercontent.com/stashapp/stash/master/docker/production/docker-compose.yml) |
| env.STASH_PORT | int | `9999` | Set the container port |
| image.pullPolicy | string | `"IfNotPresent"` | image pull policy |
| image.repository | string | `"stashapp/stash"` | image repository |
| image.tag | string | `"latest@sha256:24dbd76071745be0c4e75f730aa7ac2b37cb2b2918eabf8559643196b3b7a64a"` | image tag |
| ingress.main | object | See values.yaml | Enable and configure ingress settings for the chart under this key. |
| persistence | object | See values.yaml | Configure persistence settings for the chart under this key. |
| service | object | See values.yaml | Configures service settings for the chart. |

## Changelog

All notable changes to this application Helm chart will be documented in this file but does not include changes from our common library. To read those click [here](https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common#changelog).

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

### [3.0.0]

#### Changed

- Upgraded the common library dependency to version 4.0.0. This introduced (potentially) breaking changes to `initContainers` and `additionalContainers`. Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-4.0.0/charts/stable/common/) for the up-to-date values.

### [2.0.0]

#### Changed

- **BREAKING**: Upgraded the common library dependency to version 3.2.0. This introduces several breaking changes (`service`, `ingress` and `persistence` keys have been refactored).
  Be sure to check out the [library chart](https://github.com/k8s-at-home/library-charts/blob/common-3.2.0/charts/stable/common/) for the up-to-date values.

### [1.2.2]

#### Added

- Added icon url

### [1.0.0]

#### Added

- Initial version

[3.0.0]: #300
[2.0.0]: #200
[1.2.2]: #122
[1.0.0]: #100

## Support

- See the [Docs](https://docs.k8s-at-home.com/our-helm-charts/getting-started/)
- Open an [issue](https://github.com/k8s-at-home/charts/issues/new/choose)
- Ask a [question](https://github.com/k8s-at-home/organization/discussions)
- Join our [Discord](https://discord.gg/sTMX7Vh) community

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
