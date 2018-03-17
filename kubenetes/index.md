---
layout: page
title: Kubernetes
description: My Kubenetes learning notes and references
---

# Basics

## First App

![](img/first_app.png)

Clone this repo: [https://github.com/wardviaene/kubernetes-course](https://github.com/wardviaene/kubernetes-course)

1) Create pod from YAML file

```
$ kubectl create -f first-app/helloworld.yml
pod "nodehelloworld.example.com" created
```

### YAML File

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nodehelloworld.example.com
  labels:
    app: helloworld
spec:
  containers:
  - name: k8s-demo
    image: wardviaene/k8s-demo
    ports:
    - name: nodejs-port
      containerPort: 3000
```

2) See pod status

```
$ kubectl get pod
NAME                         READY     STATUS              RESTARTS   AGE
nodehelloworld.example.com   0/1       ContainerCreating   0          1m
```

3) See pod config

```
$ kubectl describe pod nodehelloworld.example.com
Name:         nodehelloworld.example.com
Namespace:    default
Node:         docker-for-desktop/192.168.65.3
Start Time:   Sat, 17 Mar 2018 21:12:20 +0700
Labels:       app=helloworld
Annotations:  <none>
Status:       Running
IP:           10.1.0.5
.
.
.
Events:
  Type    Reason                 Age   From                         Message
  ----    ------                 ----  ----                         -------
  Normal  Scheduled              2m    default-scheduler            Successfully assigned nodehelloworld.example.com to docker-for-desktop
  Normal  SuccessfulMountVolume  2m    kubelet, docker-for-desktop  MountVolume.SetUp succeeded for volume "default-token-ppmmf"
  Normal  Pulling                2m    kubelet, docker-for-desktop  pulling image "wardviaene/k8s-demo"
  Normal  Pulled                 13s   kubelet, docker-for-desktop  Successfully pulled image "wardviaene/k8s-demo"
  Normal  Created                13s   kubelet, docker-for-desktop  Created container
  Normal  Started                12s   kubelet, docker-for-desktop  Started container
```

4) Forward port

```
$ kubectl port-forward nodehelloworld.example.com 8081:3000
Forwarding from 127.0.0.1:8081 -> 3000
```

5) Expose service

```
$kubectl expose pod nodehelloworld.example.com --type=NodePort --name nodehelloworld-service
service "nodehelloworld-service" exposed
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

## Useful Commands

### Attach to a pod (to see logs)

```
kubectl attach nodehelloworld.example.com -i
If you don't see a command prompt, try pressing enter.
```

###  Execute command on a pod

```
$ kubectl exec nodehelloworld.example.com -- ls /app
Dockerfile
docker-compose.yml
index-db.js
index.js
misc
node_modules
package.json
```

### Run a shell in a pod

You can connect to another pod using *Endpoints* inspected by `kubectl describe service`.

```
$ kubectl run -i --tty busybox --image=busybox --restart=Never -- sh
If you don't see a command prompt, try pressing enter.
/ # telnet 10.1.0.5 3000
GET /

HTTP/1.1 200 OK
X-Powered-By: Express
Content-Type: text/html; charset=utf-8
Content-Length: 12
ETag: W/"c-7Qdih1MuhjZehB6Sv8UNjA"
Date: Sat, 17 Mar 2018 15:37:54 GMT
Connection: close

Hello World!Connection closed by foreign host
```

### Delete a pod

```
$ kubectl delete pod busybox
pod "busybox" deleted
```
