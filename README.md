# nhost

![Version: 1.1.0](https://img.shields.io/badge/Version-1.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

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
| auth.env | object | `{"AUTH_EMAIL_PASSWORDLESS_ENABLED":"true"}` | Extra env vars |
| auth.hostname | string | `"nhost.local"` | Auth hostname |
| auth.image.pullPolicy | string | `"IfNotPresent"` |  |
| auth.image.repository | string | `"nhost/hasura-auth"` |  |
| auth.image.tag | string | `"0.19.1"` |  |
| auth.logLevel | string | `"info"` | Auth log level |
| auth.replicaCount | int | `1` |  |
| auth.resources.limits.cpu | string | `"500m"` |  |
| auth.resources.limits.memory | string | `"512Mi"` |  |
| auth.resources.requests.cpu | string | `"100m"` |  |
| auth.resources.requests.memory | string | `"256Mi"` |  |
| auth.smtp | object | `{"host":"smtp.nhost.io","password":"changeme","port":25,"sender":"no-reply@nhost.io","user":"user"}` | Ignored when using Mailhog (mailhog.enabled == true) |
| commonLabels | object | `{}` | Labels to append to all resources |
| dashboard | object | `{"autoscaling":{"enabled":false,"maxReplicas":5,"minReplicas":1,"targetCPUUtilizationPercentage":80,"targetMemoryUtilizationPercentage":80},"enabled":true,"env":"prod","hostname":"nhost-dashboard.local","image":{"pullPolicy":"IfNotPresent","repository":"nhost/dashboard","tag":"0.13.10"},"replicaCount":1,"resources":{"limits":{"cpu":"500m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}}}` | NHost dashboard |
| dashboard.env | string | `"prod"` | Dashboard env mode |
| dashboard.hostname | string | `"nhost-dashboard.local"` | Dashboard hostname |
| fullnameOverride | string | `""` | String to fully override the deployment name |
| functions | object | `{"autoscaling":{"enabled":false,"maxReplicas":5,"minReplicas":1,"targetCPUUtilizationPercentage":80,"targetMemoryUtilizationPercentage":80},"enabled":true,"image":{"pullPolicy":"IfNotPresent","repository":"nhost/functions","tag":"0.1.8"},"persistence":{"size":"1Gi"},"replicaCount":1,"resources":{"limits":{"cpu":"500m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}}}` | Serverless functions |
| functions.enabled | bool | `true` | Enable serverless functions |
| functions.persistence.size | string | `"1Gi"` | Persistent volume size |
| global.dashboard | object | `{"password":"","user":"admin"}` | HTTP auth for NHost dashboard and Hasura console. Disabled when password is empty. |
| global.ingress | object | `{"annotations":{"cert-manager.io/cluster-issuer":"letsencrypt-prod"},"className":"nginx","enableTls":false}` | Shared ingress settings |
| global.logLevel | string | `"INFO"` |  |
| global.secrets.admin | string | `"nhost-admin-secret"` |  |
| global.secrets.jwtKey | string | `"5152fa850c02dc222631cca898ed1485821a70912a6e3649c49076912daa3b62182ba013315915d64f40cddfbb8b58eb5bd11ba225336a6af45bbae07ca873f3"` |  |
| global.unauthorizedRole | string | `"public"` |  |
| graphql | object | `{"autoscaling":{"enabled":false,"maxReplicas":5,"minReplicas":1,"targetCPUUtilizationPercentage":80,"targetMemoryUtilizationPercentage":80},"enableConsole":true,"hostnames":{"api":"nhost.local","console":"nhost-console.local"},"image":{"pullPolicy":"IfNotPresent","repository":"hasura/graphql-engine","tag":"v2.21.0-ce.cli-migrations-v3"},"logLevel":"info","migrations":{"enabled":false},"persistence":{"enabled":true,"size":"1Gi"},"replicaCount":1,"resources":{"limits":{"cpu":"500m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}},"unauthorizedRole":"public"}` | Main API |
| graphql.hostnames | object | `{"api":"nhost.local","console":"nhost-console.local"}` | API and console can have different hostnames |
| graphql.migrations | object | `{"enabled":false}` | persistence is required for this to work |
| graphql.persistence | object | `{"enabled":true,"size":"1Gi"}` | You can enable persistance before migrations in order to copy the needed files `kubectl cp` can be used for that |
| imagePullSecrets | list | `[]` |  |
| mailhog.enabled | bool | `true` |  |
| mailhog.ingress.enabled | bool | `true` |  |
| mailhog.ingress.hosts[0].host | string | `"mailhog.local"` |  |
| mailhog.ingress.hosts[0].paths[0].path | string | `"/"` |  |
| mailhog.ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| mailhog.ingress.ingressClassName | string | `"nginx"` |  |
| migrations | object | `{"autoscaling":{"enabled":false,"maxReplicas":5,"minReplicas":1,"targetCPUUtilizationPercentage":80,"targetMemoryUtilizationPercentage":80},"enabled":true,"hostname":"nhost-migrations.local","image":{"pullPolicy":"IfNotPresent","repository":"fpoussin/hasura-cli","tag":"v2.21.0-bind-fix"},"logLevel":"debug","replicaCount":1,"resources":{"limits":{"cpu":"500m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}}}` | Migrations API |
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
| securityContext | object | `{}` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
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
