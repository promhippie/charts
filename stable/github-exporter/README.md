# github-exporter

![Version: 7.0.9](https://img.shields.io/badge/Version-7.0.9-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 6.0.9](https://img.shields.io/badge/AppVersion-6.0.9-informational?style=flat-square)

A Helm chart for github-exporter

**Homepage:** <https://promhippie.github.io/github_exporter/>

## Installing the Chart

### OCI (Recommended)

```console
helm install github-exporter oci://ghcr.io/promhippie/charts/github-exporter
```

### Traditional

```console
helm repo add promhippie https://promhippie.github.io/charts
helm repo update
helm install github-exporter promhippie/github-exporter
```

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| tboerger | <thomas@webhippie.de> | <https://github.com/tboerger> |

## Source Code

* <https://github.com/promhippie/github_exporter>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity for the deployment |
| annotations | object | `{}` | Define additional annotations |
| collector.admin | bool | `false` | Enable collector for admin |
| collector.billing | bool | `false` | Enable collector for billing |
| collector.orgs | bool | `true` | Enable collector for orgs |
| collector.repos | bool | `true` | Enable collector for repos |
| collector.runners | bool | `false` | Enable collector for runners |
| collector.workflow_jobs | bool | `false` | Enable collector for workflow jobs |
| collector.workflow_runs | bool | `false` | Enable collector for workflow runs |
| config.appId | number | `nil` | App ID used for GitHub app |
| config.appIdKey | string | `"appId"` | Key used within secret for appId |
| config.authType | string | `"token"` | Authentication mode, could be `token` or `app` |
| config.existingSecret | string | `nil` | Existing secret to use for credentials |
| config.installationId | number | `nil` | Installation ID used for GitHub app |
| config.installationIdKey | string | `"installationId"` | Key used within secret for installationId |
| config.privateKey | string | `nil` | Private key in base64 encoded format |
| config.privateKeyKey | string | `"privateKey"` | Key used within secret for privateKey |
| config.token | string | `nil` | Access token for GitHub |
| config.tokenKey | string | `"token"` | Key used within secret for token |
| database.dsn | string | `"sqlite:///var/lib/exporter/database.sqlite3"` | DSN for used database and credentials |
| database.dsnKey | string | `"dsn"` | Key used within secret for webhook |
| database.enabled | bool | `false` | Enable database secret integration |
| database.existingSecret | string | `nil` | Existing secret to use for credentials |
| envFromConfigMap | string | `""` | Environment variables from existing configmap |
| envFromSecret | string | `""` | environment variables from existing secret |
| exporter.enterprises | string | `nil` | Enterprises to scrape metrics from |
| exporter.orgs | string | `nil` | Organizations to scrape metrics from |
| exporter.repos | string | `nil` | Repositories to scrape metrics from |
| extraEnvSecrets | object | `{}` | Extra environment variables from secrets |
| extraEnvVariables | object | `{}` | Extra environment variables from mapping |
| extraInitContainers | list | `[]` | List of extra init containers |
| extraVolumeMounts | list | `[]` | List of extra volume mounts |
| extraVolumes | list | `[]` | List of extra volumes |
| files | object | `{}` | List of files written to a configmap and mounted to /etc/github-exporter-files |
| fullnameOverride | string | `""` | Override the fullname |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.pullSecrets | list | `[]` | Optional name of pull secret if using a private registry |
| image.repository | string | `"quay.io/promhippie/github-exporter"` | Image repository used by deployment |
| image.tag | string | `""` | Optional tag for the repository, defaults to app version |
| ingress.annotations | object | `{}` | Additional annotations for the ingress |
| ingress.className | string | `nil` | Class name for the ingress resource |
| ingress.enabled | bool | `false` | Enable ingress |
| ingress.hosts | list | `[{"host":"example.local","paths":[{"path":"/","pathType":"Prefix"}]}]` | Host definition for ingress |
| ingress.labels | object | `{}` | Additional labels for the ingress |
| ingress.tls | list | `[]` | Optional TLS configuration for ingress |
| labels | object | `{}` | Define additional labels |
| nameOverride | string | `""` | Override the name |
| nodeSelector | object | `{}` | Node selector for the deployment |
| persistence.accessModes | list | `["ReadWriteOnce"]` | Access modes used for the exporter volume |
| persistence.enabled | bool | `false` | Enable persistence for the exporter |
| persistence.existingClaim | string | `nil` | Name of an already existing claim |
| persistence.mountPath | string | `"/var/lib/exporter"` | Path to mount the exporter volume |
| persistence.size | string | `"1G"` | Size for the exporter volume |
| persistence.storageClass | string | `nil` | Storage class used for the exporter volume |
| podSecurityContext | object | `{"allowPrivilegeEscalation":false,"capabilities":{"drop":["all"]},"readOnlyRootFilesystem":true,"runAsGroup":10000,"runAsNonRoot":true,"runAsUser":10000}` | Security context for the pod |
| prometheusRule.additionalLabels | object | `{}` | Additional labels for prometheus rules |
| prometheusRule.enabled | bool | `false` | Enable custom prometheus rules |
| prometheusRule.namespace | string | `""` | Namespace used by prometheus rules |
| prometheusRule.rules | list | `[]` | Rules definition |
| replicaCount | int | `1` | Replicas for the deployment |
| resources | object | `{}` | Resources for the deployment |
| securityContext | object | `{"fsGroup":10000}` | Security context for the deployment |
| service.annotations | object | `{}` | Additional annotations for the service |
| service.internalPort | int | `9504` | Internal port of the service |
| service.labels | object | `{}` | Additional labels for the service |
| service.port | int | `9504` | Port of the service |
| service.type | string | `"ClusterIP"` | Type of the service |
| serviceAccount.create | bool | `true` | Create a new service account |
| serviceAccount.name | string | `""` | Optional name for an existing service account |
| serviceMonitor.enabled | bool | `false` | Enable service monitor integration |
| serviceMonitor.interval | string | `"30s"` | Scrape interval |
| serviceMonitor.jobLabel | string | `nil` | Optionally override the job label |
| serviceMonitor.labels | object | `{}` | Additional labels for the service monitor |
| serviceMonitor.metricRelabelings | list | `[]` | Metric relabeling configuration |
| serviceMonitor.namespace | string | `""` | Namespace used by service monitor |
| serviceMonitor.relabelings | list | `[]` | Relabeling configuration |
| serviceMonitor.targetLabels | list | `[]` | Target labels |
| serviceMonitor.telemetryPath | string | `"/metrics"` | Scrape path |
| serviceMonitor.timeout | string | `"30s"` | Scrape timeout |
| tolerations | list | `[]` | Tolerations for the deployment |
| updateStrategy | object | `{"type":"RollingUpdate"}` | Update strategy for the deployment |
| webhook.enabled | bool | `false` | Enable webhook secret integration |
| webhook.existingSecret | string | `nil` | Existing secret to use for credentials |
| webhook.path | string | `nil` | Path for webhook endpoint |
| webhook.secret | string | `nil` | Secret for webhook authentication |
| webhook.secretKey | string | `"secret"` | Key used within secret for webhook |
| workflow_job.labels | list | `[]` | List of labels assigned for workflow metrics |
| workflow_job.window | string | `"24h"` | Duration to keep workflow metrics |
| workflow_run.labels | list | `[]` | List of labels assigned for workflow metrics |
| workflow_run.window | string | `"24h"` | Duration to keep workflow metrics |
