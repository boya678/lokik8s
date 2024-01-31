#agregar repo

helm repo add grafana https://grafana.github.io/helm-charts

#actualizar repo
helm repo update

#instalar loki
En el values-loki en el primer renglon se encuentra el tiempo de retencion 1440h

helm upgrade --install --namespace monitoring --create-namespace loki grafana/loki --values values-loki.yaml --version 5.8.5

#instalar promptail
helm upgrade --install --namespace monitoring --create-namespace promtail grafana/promtail --values values-promptail.yaml --version 6.11.5
