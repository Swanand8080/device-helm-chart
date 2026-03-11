| Variable | Requirement | Default (if applicable) | Description |
| :--- | :--- | :--- | :--- |
| `image.repository` | Mandatory | - | The container image name/path. |
| `device.targetPort` | Mandatory | - | Port where the application listens for device traffic. |
| `ingress.host` | Mandatory | - | Primary DNS hostname for the main application. |
| `ingress.device.host` | Mandatory | - | DNS hostname for the device-specific service. |
| `ingress.tlsSecretName` | Mandatory | - | Kubernetes Secret containing SSL/TLS certificates. |
| `replicaCount` | Optional | `1` | Number of running pod instances. |
| `image.tag` | Optional | `latest` | The specific version of the container image. |
| `timezone` | Optional | `Asia/Kolkata` | Sets the system timezone via the TZ environment variable. |
| `service.type` | Optional | `ClusterIP` | Kubernetes Service type (e.g., NodePort, LoadBalancer). |
| `service.port` | Optional | `80` | External port for the main application service. |
| `service.targetPort` | Optional | `80` | Internal container port for the main application. |
| `device.port` | Optional | `80` | External port for the device service. |
| `ingress.enabled` | Optional | - | Toggle to create or skip Ingress resources. |
| `ingress.ingressClassName` | Optional | `nginx` | Specifies the Ingress controller to use. |
| `ingress.annotations` | Optional | - | Map of custom settings for the Ingress controller. |
| `livenessProbe.enabled` | Optional | - | Toggles the liveness health check. |
| `livenessProbe.path` | Optional | `/health` | Endpoint for liveness status checks. |
| `readinessProbe.enabled` | Optional | - | Toggles the readiness health check. |
| `readinessProbe.path` | Optional | `/ready` | Endpoint for readiness status checks. |
| `nodeAffinity.enabled` | Optional | - | Enables placement rules for specific Kubernetes nodes. |
| `nodeAffinity.config` | Optional | - | The specific affinity rules and expressions. |
| `extraEnv` | Optional | - | List of additional environment variables to inject. |
