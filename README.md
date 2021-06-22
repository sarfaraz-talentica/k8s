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


## Output:
```
gauravh@GauravH-ub:~/deserve/deserve-k8s$ curl localhost
{"message":"Hello Deserve","branches":"US, Pune, Banglore","container_name":"myapp-599bbc7bfb-27rqq"}
gauravh@GauravH-ub:~/deserve/deserve-k8s$ curl localhost
{"message":"Hello Deserve","branches":"US, Pune, Banglore","container_name":"myapp-599bbc7bfb-jlrk6"}
gauravh@GauravH-ub:~/deserve/deserve-k8s$ curl localhost
{"message":"Hello Deserve","branches":"US, Pune, Banglore","container_name":"myapp-599bbc7bfb-jlrk6"}
gauravh@GauravH-ub:~/deserve/deserve-k8s$ curl localhost
{"message":"Hello Deserve","branches":"US, Pune, Banglore","container_name":"myapp-599bbc7bfb-27rqq"}

```
