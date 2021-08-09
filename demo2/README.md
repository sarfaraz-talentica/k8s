# Kind

Refer this for Setup ([Kind](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)):

## 1.1 Kind cluster
```
kind create cluster --config kind-config.yaml
```

## 1.2 Install Ingress
```
kubectl  apply -f nginx-ingress/nginx-ingress.yaml
```

## 1.3 Install ArgoCD
```
kubectl create namespace argocd
kubectl  apply -n argocd -f argo-cd/install.yaml 
```
##  Deploy ([App](./goApp)) from argoCD

