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
<<<<<<< HEAD
> username : admin

> password : kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

##  Deploy ([App](./goApp)) app from argoCD
=======
##  Deploy ([App](./goApp)) from argoCD
>>>>>>> ecebee29b1cd3353ff6d2500dc6387f890eaef86

