# Despliegue de una Aplicación con Argo CD y Kubernetes (GitOps)

Repositorio declarativo para el despliegue automatizado de una aplicación web en Kubernetes mediante Argo CD.

## Estructura del Proyecto

- `manifests/deployment.yml`: Deployment con 2 réplicas iniciales, etiquetas `app: web-gitops-app` y definición de `requests` y `limits` de CPU y memoria.
- `manifests/service.yml`: Service de tipo `NodePort` (puerto `30080`) apuntando al puerto `80` de los Pods.
- `manifests/hpa.yml`: Horizontal Pod Autoscaler (`autoscaling/v2`) configurado entre 2 y 5 réplicas con un umbral objetivo del 50% de uso de CPU.
- `argocd-app.yml`: Manifiesto declarativo opcional de la aplicación en Argo CD con sincronización automática (`Automated Sync`).
