## Kind Setup 
https://kind.sigs.k8s.io/docs/user/quick-start/#installation

## Kind cluster
```
kind create cluster --config kind-config.yaml
```

## Install Ingress
```
kubectl  apply -f nginx-ingress/nginx-ingress.yaml
```

## Install ArgoCD
```
kubectl create namespace argocd
kubectl  apply -n argocd -f argo-cd/install.yaml 
```