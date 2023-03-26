# nhost

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

A Helm chart for Kubernetes

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | minio | 12.2.1 |
| https://charts.bitnami.com/bitnami | postgresql | 12.2.6 |
| https://codecentric.github.io/helm-charts | mailhog | 5.2.3 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| auth.autoscaling.enabled | bool | `false` |  |
| auth.autoscaling.maxReplicas | int | `5` |  |
| auth.autoscaling.minReplicas | int | `1` |  |
| auth.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| auth.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| auth.enabled | bool | `true` | Hasura-auth can be disabled when using an external auth prodiver |
| auth.env.AUTH_EMAIL_PASSWORDLESS_ENABLED | string | `"true"` |  |
| auth.image.pullPolicy | string | `"IfNotPresent"` |  |
| auth.image.repository | string | `"nhost/hasura-auth"` |  |
| auth.image.tag | string | `"0.19.1"` |  |
| auth.logLevel | string | `"info"` |  |
| auth.replicaCount | int | `1` |  |
| auth.resources.limits.cpu | string | `"500m"` |  |
| auth.resources.limits.memory | string | `"512Mi"` |  |
| auth.resources.requests.cpu | string | `"100m"` |  |
| auth.resources.requests.memory | string | `"256Mi"` |  |
| auth.smtp | object | `{"host":"smtp.nhost.io","password":"changeme","port":25,"sender":"no-reply@nhost.io","user":"user"}` | Ignored when using Mailhog (mailhog.enabled == true) |
| commonLabels | object | `{}` | Labels to append to all resources |
| dashboard.autoscaling.enabled | bool | `false` |  |
| dashboard.autoscaling.maxReplicas | int | `5` |  |
| dashboard.autoscaling.minReplicas | int | `1` |  |
| dashboard.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| dashboard.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| dashboard.enabled | bool | `true` |  |
| dashboard.env | string | `"prod"` |  |
| dashboard.hostname | string | `"nhost-dashboard.local"` |  |
| dashboard.image.pullPolicy | string | `"IfNotPresent"` |  |
| dashboard.image.repository | string | `"nhost/dashboard"` |  |
| dashboard.image.tag | string | `"0.13.9"` |  |
| dashboard.replicaCount | int | `1` |  |
| dashboard.resources.limits.cpu | string | `"500m"` |  |
| dashboard.resources.limits.memory | string | `"512Mi"` |  |
| dashboard.resources.requests.cpu | string | `"100m"` |  |
| dashboard.resources.requests.memory | string | `"256Mi"` |  |
| fullnameOverride | string | `""` | String to fully override the deployment name |
| functions.autoscaling.enabled | bool | `false` |  |
| functions.autoscaling.maxReplicas | int | `5` |  |
| functions.autoscaling.minReplicas | int | `1` |  |
| functions.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| functions.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| functions.image.pullPolicy | string | `"IfNotPresent"` |  |
| functions.image.repository | string | `"nhost/functions"` |  |
| functions.image.tag | string | `"0.1.8"` |  |
| functions.persistence.size | string | `"1Gi"` |  |
| functions.replicaCount | int | `1` |  |
| functions.resources.limits.cpu | string | `"500m"` |  |
| functions.resources.limits.memory | string | `"512Mi"` |  |
| functions.resources.requests.cpu | string | `"100m"` |  |
| functions.resources.requests.memory | string | `"256Mi"` |  |
| graphql.autoscaling.enabled | bool | `false` |  |
| graphql.autoscaling.maxReplicas | int | `5` |  |
| graphql.autoscaling.minReplicas | int | `1` |  |
| graphql.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| graphql.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| graphql.enableConsole | bool | `true` |  |
| graphql.image.pullPolicy | string | `"IfNotPresent"` |  |
| graphql.image.repository | string | `"hasura/graphql-engine"` |  |
| graphql.image.tag | string | `"v2.21.0"` |  |
| graphql.logLevel | string | `"debug"` |  |
| graphql.replicaCount | int | `1` |  |
| graphql.resources.limits.cpu | string | `"500m"` |  |
| graphql.resources.limits.memory | string | `"512Mi"` |  |
| graphql.resources.requests.cpu | string | `"100m"` |  |
| graphql.resources.requests.memory | string | `"256Mi"` |  |
| graphql.unauthorizedRole | string | `"public"` |  |
| imagePullSecrets | list | `[]` |  |
| mailhog.enabled | bool | `true` |  |
| mailhog.ingress.enabled | bool | `true` |  |
| mailhog.ingress.hosts[0].host | string | `"mailhog.local"` |  |
| mailhog.ingress.hosts[0].paths[0].path | string | `"/"` |  |
| mailhog.ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| mailhog.ingress.ingressClassName | string | `"nginx"` |  |
| minio.auth.forceNewKeys | bool | `true` |  |
| minio.auth.rootPassword | string | `"youshouldchangethis"` |  |
| minio.auth.rootUser | string | `"admin"` |  |
| minio.defaultBuckets | string | `"nhost"` |  |
| minio.enabled | bool | `true` |  |
| minio.persistence.size | string | `"1Gi"` |  |
| nameOverride | string | `""` | String to partially override the deployment name (will maintain the release name) |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| postgresql.auth.database | string | `"nhost"` |  |
| postgresql.auth.enablePostgresUser | bool | `true` |  |
| postgresql.auth.password | string | `"changemeaswell"` |  |
| postgresql.auth.postgresPassword | string | `"changethisadminpassword"` |  |
| postgresql.auth.username | string | `"nhost"` |  |
| postgresql.enabled | bool | `true` |  |
| postgresql.image.debug | bool | `true` |  |
| postgresql.primary.initdb.scripts."0001-create-schema.sql" | string | `"CREATE SCHEMA IF NOT EXISTS auth;\nCREATE SCHEMA IF NOT EXISTS storage;\nCREATE EXTENSION IF NOT EXISTS pgcrypto WITH SCHEMA public;\nCREATE EXTENSION IF NOT EXISTS citext WITH SCHEMA public;\nCREATE OR REPLACE FUNCTION public.set_current_timestamp_updated_at() RETURNS trigger LANGUAGE plpgsql AS $$\ndeclare _new record;\nbegin _new := new;\n_new.\"updated_at\" = now();\nreturn _new;\nend;\n$$;\n"` |  |
| postgresql.primary.persistence.size | string | `"1Gi"` |  |
| postgresql.volumePermissions.enabled | bool | `true` |  |
| secrets.admin | string | `"nhost-admin-secret"` |  |
| secrets.jwtKey | string | `"5152fa850c02dc222631cca898ed1485821a70912a6e3649c49076912daa3b62182ba013315915d64f40cddfbb8b58eb5bd11ba225336a6af45bbae07ca873f3"` |  |
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| settings.enableConsole | bool | `true` |  |
| settings.ingress.annotations."cert-manager.io/cluster-issuer" | string | `"letsencrypt-prod"` |  |
| settings.ingress.className | string | `"nginx"` |  |
| settings.ingress.enableTls | bool | `false` |  |
| settings.ingress.hostname | string | `"nhost.local"` |  |
| settings.logLevel | string | `"DEBUG"` |  |
| settings.unauthorizedRole | string | `"public"` |  |
| storage.autoscaling.enabled | bool | `false` |  |
| storage.autoscaling.maxReplicas | int | `5` |  |
| storage.autoscaling.minReplicas | int | `1` |  |
| storage.autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| storage.autoscaling.targetMemoryUtilizationPercentage | int | `80` |  |
| storage.image.pullPolicy | string | `"IfNotPresent"` |  |
| storage.image.repository | string | `"nhost/hasura-storage"` |  |
| storage.image.tag | string | `"0.3.4"` |  |
| storage.replicaCount | int | `1` |  |
| storage.resources.limits.cpu | string | `"500m"` |  |
| storage.resources.limits.memory | string | `"512Mi"` |  |
| storage.resources.requests.cpu | string | `"100m"` |  |
| storage.resources.requests.memory | string | `"256Mi"` |  |
| storage.s3 | object | `{"access_key":"","bucket":"","endpoint":"","secret_key":""}` | Ignored when using Minio |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.11.0](https://github.com/norwoodj/helm-docs/releases/v1.11.0)
