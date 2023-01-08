# lupa

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: v0.0.1](https://img.shields.io/badge/AppVersion-v0.0.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

Lupa Helm chart for Kubernetes

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity configuration for pods |
| autoscaling.enabled | bool | `false` | Whether to enable deployment autoscaling |
| autoscaling.maxReplicas | int | `10` | Maximum autoscaling replicas |
| autoscaling.minReplicas | int | `1` | Minimum autoscaling replicas |
| autoscaling.targetCPUUtilizationPercentage | int | `80` | Target CPU utilization percentage |
| autoscaling.targetMemoryUtilizationPercentage | int | `nil` | Target memory utilization percentage |
| collectorConfig | string | `"receivers:\n  otlp:\n    protocols:\n      grpc:\n      http:\nprocessors:\n  batch:\nexporters:\n  # elasticsearch:\n  #   endpoints: [\"http://elastic-svc.elastic-ns:9200/\"]\n  #   username: \"elastic\"\n  #   password: \"password\"\nservice:\n  pipelines:\n    traces:\n      receivers: [otlp]\n      processors: [batch]\n      # exporters: [elasticsearch]\n"` | Lupa OpenTelemetry collector config |
| env | object | `{"API_PORT":"8080","DEBUG":"false"}` | Environment variables to add |
| fullnameOverride | string | `""` | Overrides the chart computed fullname |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.repository | string | `"epsagon/lupa"` | Image repository |
| image.tag | string | `""` | Image tag. Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Image pull secrets for the image registry |
| ingress.additionalIngresses | list | `[]` | Additional ingresses for when differently annotated ingress services are required. Each additional ingress needs "name" key set to something unique. Created if ingress.enabled set to true. |
| ingress.annotations | object | `{}` | Annotations for ingress |
| ingress.className | string | `""` | Ingress class name to identify ingress controllers |
| ingress.enabled | bool | `false` | Whether to enable ingress |
| ingress.hosts | list | `[]` | Ingress host names with their path names |
| ingress.tls | list | `[]` | Ingress TLS configuration |
| nameOverride | string | `""` | Overrides the chart name |
| nodeSelector | object | `{}` | Node selector for pods |
| podAnnotations | object | `{}` | Annotations for pods |
| podSecurityContext | object | `{}` | Pod-level security configuration |
| ports.lupa-api.containerPort | int | `8080` | Container port for API |
| ports.lupa-api.enabled | bool | `true` | Whether to enable port for the API (+frontend) |
| ports.lupa-api.protocol | string | `"TCP"` | Protocol to use for API |
| ports.lupa-api.servicePort | int | `8080` | Service port for API |
| ports.otlp-grpc.containerPort | int | `4317` | Container port for OTLP gRPC |
| ports.otlp-grpc.enabled | bool | `true` | Whether to enable port for OTLP gRPC |
| ports.otlp-grpc.protocol | string | `"TCP"` | Protocol to use for OTLP gRPC |
| ports.otlp-grpc.servicePort | int | `4317` | Service port for OTLP gRPC |
| ports.otlp-http.containerPort | int | `4318` | Container port for OTLP HTTP |
| ports.otlp-http.enabled | bool | `true` | Whether to enable port for OTLP HTTP |
| ports.otlp-http.protocol | string | `"TCP"` | Protocol to use for OTLP HTTP |
| ports.otlp-http.servicePort | int | `4318` | Service port for OTLP HTTP |
| replicaCount | int | `1` | Number of replicas to use. Ignored if `autoscaling.enabled` is set to `true`. |
| resources | object | `{}` | Resource requests and limits |
| securityContext | object | `{}` | Container-level security configuration |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template. |
| tolerations | list | `[]` | Tolerations for pods |
