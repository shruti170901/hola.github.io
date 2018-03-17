---
layout: page
title: Kubernetes
description: My Kubenetes learning notes and references
---

# Basics

## First App

Clone this repo: https://github.com/wardviaene/kubernetes-course

1) Create pod

```
kubectl create -f first-app/helloworld.yml
```

2) See pod status

```
kubectl get pod
```

3) See pod config

```
kubectl describe pod nodehelloworld.example.com
```

4) Forward port

```
kubectl port-forward nodehelloworld.example.com 8081:3000
```

5) Expose service

```
kubectl expose pod nodehelloworld.example.com --type=NodePort --name nodehelloworld-service
```

6) See list of service

```
$ kubectl get service
NAME                     TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)          AGE
kubernetes               ClusterIP   10.96.0.1      <none>        443/TCP          1h
nodehelloworld-service   NodePort    10.97.86.198   <none>        3000:31543/TCP   14m
```

7) Get service url

```
$ kubectl describe service nodehelloworld-service
Name:                     nodehelloworld-service
Namespace:                default
Labels:                   app=helloworld
Annotations:              <none>
Selector:                 app=helloworld
Type:                     NodePort
IP:                       10.97.86.198
LoadBalancer Ingress:     localhost
Port:                     <unset>  3000/TCP
TargetPort:               3000/TCP
NodePort:                 <unset>  31543/TCP
Endpoints:                10.1.0.5:3000
Session Affinity:         None
External Traffic Policy:  Cluster
Events:                   <none>
```

8) Test accessing app at `http://localhost:31543/`
