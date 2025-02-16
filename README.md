```shell
## add prometheus repository
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

## update helm repos
helm repo update

## install/upgrade prometheus
helm upgrade --install prometheus-operator prometheus-community/kube-prometheus-stack \
    -f kube-prometheus-stack/values.yaml \
    --namespace monitoring \
    --create-namespace \
    --set prometheus.prometheusSpec.externalLabels.cluster=<cluster_name> \
    --kube-context=<cluster_name>
```
