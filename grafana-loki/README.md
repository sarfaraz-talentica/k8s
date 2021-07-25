```
helm repo add grafana https://grafana.github.io/helm-charts
```
```
helm repo update
```
```
helm show values  grafana/loki-stack > loki-stack-values.yaml
```
```
helm install loki-stack grafana/loki-stack --values loki-stack-values.yaml -n loki --create-namespace
```
To get the admin password for the Grafana pod, run the following command:

```
kubectl get secret --namespace loki-stack loki-stack-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo
```

To access the Grafana UI, run the following command:
```
kubectl port-forward --namespace loki-stack service/loki-grafana 3000:80
```
