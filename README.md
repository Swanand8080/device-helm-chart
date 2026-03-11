| Variable | Default (if applicable) | Description |
| :--- | :--- | :--- |
| `image.repository` | - | The container image name/path. |
| `device.targetPort` | - | Port where the application listens for device traffic. |
| `ingress.host` | - | Primary DNS hostname for the main application. |
| `ingress.device.host` | - | DNS hostname for the device-specific service. |
| `ingress.tlsSecretName` | - | Kubernetes Secret containing SSL/TLS certificates. |
| `replicaCount` | `1` | Number of running pod instances. |
| `image.tag` | `latest` | The specific version of the container image. |
| `timezone` | `Asia/Kolkata` | Sets the system timezone via the TZ environment variable. |
| `service.type` | `ClusterIP` | Kubernetes Service type (e.g., NodePort, LoadBalancer). |
| `service.port` | `80` | External port for the main application service. |
| `service.targetPort` | `80` | Internal container port for the main application. |
| `device.port` | `80` | External port for the device service. |
| `ingress.enabled` | - | Toggle to create or skip Ingress resources. |
| `ingress.ingressClassName` | `nginx` | Specifies the Ingress controller to use. |
| `ingress.annotations` | - | Map of custom settings for the Ingress controller. |
| `livenessProbe.enabled` | - | Toggles the liveness health check. |
| `livenessProbe.path` | `/health` | Endpoint for liveness status checks. |
| `readinessProbe.enabled` | - | Toggles the readiness health check. |
| `readinessProbe.path` | `/ready` | Endpoint for readiness status checks. |
| `nodeAffinity.enabled` | - | Enables placement rules for specific Kubernetes nodes. |
| `nodeAffinity.config` | - | The specific affinity rules and expressions. |
| `extraEnv` | - | List of additional environment variables to inject. |


Example:
helm upgrade --install device-app-release ./device-helm-chart \
  --set image.repository=my-docker-repo/app \
  --set image.tag=v1.2.0 \
  --set replicaCount=2 \
  --set device.targetPort=9000 \
  --set ingress.host=app.example.com \
  --set ingress.device.host=device.example.com \
  --set ingress.tlsSecretName=prod-tls-cert \
  --set livenessProbe.enabled=true \
  --set readinessProbe.enabled=true
