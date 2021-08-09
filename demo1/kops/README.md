# Istalling Kops

Refer this ([kops](https://zero-to-jupyterhub.readthedocs.io/en/latest/kubernetes/amazon/step-zero-aws.html)):

```
export KOPS_STATE_STORE=s3://prodtechdevops

kops create cluster --name=prod.techdevops.ml \
--state=s3://prodtechdevops \
--zones=ap-south-1a \
--node-size t2.micro \
--node-count=3 \
--master-size t2.medium \
--master-count 1
```

Must specify --yes to apply changes

## 1.1 Deploy Nginx Ingress controller
```
kubectl apply -f nginx/nginx.yaml
```

## 1.1 Deploy Cert-Manager
```
kubectl apply -f cert-manager/cert-manager.yaml
```


