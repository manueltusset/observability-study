```shell
## add prometheus repository
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

## update helm repos
helm repo update

## install/upgrade prometheus
helm upgrade --install prometheus-agent prometheus-community/prometheus \
             -n monitoring \
             -f prometheus-agent/values.yaml \
             --set server.global.external_labels.cluster=<cluster_name> \
             --create-namespace \
             --kube-context=<cluster_name>
```
