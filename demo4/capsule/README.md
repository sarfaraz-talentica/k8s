# Kind

Refer this for Setup ([Kind](https://kind.sigs.k8s.io/docs/user/quick-start/#installation)):

## Kind cluster

> kind create cluster --config kind-config.yaml

## Add this repository:

> helm repo add clastix https://clastix.github.io/charts

## Create the Namespace:

> kubectl create namespace capsule-system

## Install the Chart:
> helm install capsule clastix/capsule -n capsule-system

## Show the status:
> helm status capsule -n capsule-system

## Upgrade the Chart
> helm upgrade capsule clastix/capsule -n capsule-system

## Uninstall the Chart

> helm uninstall capsule -n capsule-system


## Now Create a Tenant

> kubectl apply -g tenant.yaml

```
kubectl get tenant
NAME   NAMESPACE QUOTA   NAMESPACE COUNT   OWNER NAME   OWNER KIND   NODE SELECTOR                  AGE
oil    3                 0                 alice        User         {"kubernetes.io/os":"linux"}   2m59s
```

## Create Kubeconfig file for alice user for tenant Oil.

> ./create-user.sh alice oil

```
export KUBECONFIG=alice-oil.kubeconfig
```
## Try to create NS more than Quota

```
kubectl create ns a
namespace/a created
```
```
kubectl create ns b
namespace/b created
```
```
kubectl create ns c
namespace/c created
```
```
kubectl create ns d
Error from server (Cannot exceed Namespace quota: please, reach out to the system administrators): admission webhook "quota.namespace.capsule.clastix.io" denied the request: Cannot exceed Namespace quota: please, reach out to the system administrators
```

