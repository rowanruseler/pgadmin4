###### based on [dpage/pgadmin4]

# Helm Chart for pgAdmin

#### Table of Contents

1. [Overview][Overview]
2. [Description][Description]
3. [Setup][Setup]

## Overview

## Notices

This helm chart requires, if ingress is enabled:

* [cert-manager]
  * configured with [letsencrypt]

## Description

pgAdmin is a web based administration tool for PostgreSQL database.

## Setup

### Configuration

| Parameter | Description | Default |
| --------- | ----------- | ------- |
| `replicaCount` | Number of pgadmin replicas | `1` |
| `image.tag` | Image tag | `latest` |
| `ingress.enabled` | Enable Client Ingress | `true` |
| `ingress.hosts` | Client Ingress Hostnames | `pgadmin.domain.com` |
| `ingress.tls` | Client Ingress TLS configuration | `[]` |
| `ingress.tls.secretName` | Client Ingress TLS Secretname | `pgadmin-tls` |
| `ingress.tls.hosts` | Client Ingress TLS Hostnames | `pgadmin.domain.com` |
| `environment.username` | pgAdmin default email | `pgadmin@domain.com` |
| `environment.password` | pgAdmin default password | `SuperSecret` |
| `persistence` | Persistent enabled/disabled | `true` |
| `persistence.accessMode` | persistent Access Mode | `ReadWriteOnce` |
| `persistence.size` | persistent volume size | `10Gi` |
| `resources` | CPU/memory resource requests/limits | `` |
| `nodeSelector` | Node labels for pod assignment | `{}` |
| `tolerations` | Node tolerations for pod assignment | `[]` |
| `affinity` | Node affinity for pod assignment | `{}` |

### Install

Install the pgAdmin helm chart with a release name:

```
helm install --name pgadmin .
```

### Remove

Remove the pgAdmin helm chart:

```
helm delete --purge pgadmin
```

[Overview]: #overview
[Description]: #description
[Setup]: #setup

[dpage/pgadmin4]: https://hub.docker.com/r/dpage/pgadmin4
[cert-manager]: https://github.com/helm/charts/tree/master/stable/cert-manager
[letsencrypt]: https://letsencrypt.org/
