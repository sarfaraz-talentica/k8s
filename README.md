## Kind Setup 
https://kind.sigs.k8s.io/docs/user/quick-start/#installation

## Kind cluster
```
kind create cluster --config kind-config.yaml
```

## Install Ingress
```
kubectl  apply -f nginx-ingress.yaml
```

## Deploy app in Kind
```
kubectl  apply -f deserve.yaml
```

