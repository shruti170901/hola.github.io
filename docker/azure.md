---
layout: default
---

# 1. Deploy

1) Go to https://store.docker.com/editions/community/docker-ce-azure and select preferred version. It will lunch Azure console.

![Get Docker Azure Stable](/uploads/docker/get-docker-azure-stable.png "Get Docker Azure Stable")

2) Fill in the form and click *Purchase* to start deployment

![Docker Template Azure](/uploads/docker/docker-template-azure.png "Docker Template Azure")

![Agree And Purchase](/uploads/docker/agree-and-purchase.png "Agree And Purchase")

3) It take only one or two minutes to complete.

![Deploy In Progress](/uploads/docker/deploy-in-progress.png "Deploy In Progress")

4) Here is what you see in the resource group

![Resource Group](/uploads/docker/resource-group.png "Resource Group")

> For more information, visit https://docs.docker.com/docker-for-azure/#configuration

# 2. Connect

1) Click on *externalSSHLoadBalancer*

![External Ssh Load Balancer](/uploads/docker/external-ssh-load-balancer.png "External Ssh Load Balancer")

2) Go to *Inbound NAT rules* and take note of IP and port of the manager you want to connect

![Nat Rule Ip Port](/uploads/docker/nat-rule-ip-port.png "Nat Rule Ip Port")

3) Connect to the manager using `ssh`

```
ssh -p <port> docker@<ip>
```

![Ssh Docker](/uploads/docker/ssh-docker.png "Ssh Docker")

> For more information, visit https://docs.docker.com/docker-for-azure/deploy/#connecting-to-your-manager-nodes-using-ssh

# 3. Init Swarm

1) Use command `docker node ls`. If it says something like below then you need init the Swarm.

```
Error response from daemon: This node is not a swarm manager. Use "docker swarm init" or "docker swarm join" to connect this node to swarm and try again.
```

2) Use command `docker swarm init`

```
swarm-manager000000:~$ docker swarm init
Swarm initialized: current node (vtg0wclx2sgbrlw0bl9pqjoeb) is now a manager.

To add a worker to this swarm, run the following command:

    docker swarm join --token xxxxxxxxxxxxxxxxxxx 10.0.0.4:2377

To add a manager to this swarm, run 'docker swarm join-token manager' and follow the instructions.
```

3) Use command `docker node ls` again and you should see something like this:

```
swarm-manager000000:~$ docker node ls
ID                            HOSTNAME              STATUS              AVAILABILITY        MANAGER STATUS      ENGINE VERSION
vtg0wclx2sgbrlw0bl9pqjoeb *   swarm-manager000000   Ready               Active              Leader              18.03.0-ce
```

# 4. Join Worker Node

1) You can only connect to worker nodes from manager node. But before you can connect, you need SSH key in the manager node by using command `scp` in your local PC like this:

```
$ scp -P 50000 ~/.ssh/id_rsa* docker@52.148.92.173:~/.ssh
id_rsa
id_rsa.pub
```

2) Next, you need to know the IP of your worker. Go to Virtual Network to see the IP of your worker.

![Virtual Network](/uploads/docker/virtual-network.png "Virtual Network")

![Swarm Worker Ip](/uploads/docker/swarm-worker-ip.png "Swarm Worker Ip")

3) Use command `docker swarm join-token worker` to get the join token.

```
swarm-manager000000:~$ docker swarm join-token worker
To add a worker to this swarm, run the following command:

    docker swarm join --token SWMTKN-1-xxxxx-xxxxxx 10.0.0.4:2377
```

4) Now, you can connect to your worker from your manager.

```
swarm-manager000000:~$ ssh 10.0.0.5
The authenticity of host '10.0.0.5 (10.0.0.5)' can't be established.
RSA key fingerprint is SHA256:xxxxxxxxx/xxxxxxxxxx.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added '10.0.0.5' (RSA) to the list of known hosts.
Welcome to Docker!
```
5) Use command you got from 3)

```
swarm-worker000000:~$ docker swarm join --token SWMTKN-1-xxxxxx-xxxxxx 10.0.0.4:2377
This node joined a swarm as a worker.
```

6) Exit to manager node and see the list of node again. You should see both manager and worker in the list.

```
swarm-manager000000:~$ docker node ls
ID                            HOSTNAME              STATUS              AVAILABILITY        MANAGER STATUS      ENGINE VERSION
vtg0wclx2sgbrlw0bl9pqjoeb *   swarm-manager000000   Ready               Active              Leader              18.03.0-ce
nyieyjio2ai7kh4ev0szgeyjc     swarm-worker000000    Ready               Active                                  18.03.0-ce
```