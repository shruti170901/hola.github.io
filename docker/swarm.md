---
layout: default
---

# Swarm Basics
## Containers Everywhere = New Problems
- How do we automate container lifecycle?
- How can we easily scale out/in/up/down?
- How can we ensure our containers are re-created if they fail?
- How can we replace containers without downtime (blue/green
deploy)?
- How can we control/track where containers get started?
- How can we create cross-node virtual networks?
- How can we ensure only trusted servers run our containers?
- How can we store secrets, keys, passwords and get them to the right
container (and only that container)?

## Swarm Mode: Built-In Orchestration
- Swarm Mode is a clustering solution built inside Docker
- Not related to Swarm "classic" for pre-1.12 versions
- Added in 1.12 (Summer 2016) via SwarmKit toolkit
- Enhanced in 1.13 (January 2017) via Stacks and Secrets
- Not enabled by default, new commands once enabled
    - docker swarm
    - docker node
    - docker service
    - docker stack
    - docker secret
## Swarm Architecture
![Swarm Mode](/uploads/swarm/swarm-mode.png "Swarm Mode")

![Swarm Topology](/uploads/swarm/swarm-topology.png "Swarm Topology")

![Nginx On Swarm](/uploads/swarm/nginx-on-swarm.png "Nginx On Swarm")

![Swarm Architecture](/uploads/swarm/swarm-architecture.png "Swarm Architecture")
# Swarm Initialization
`docker info | grep Swarm` See whether swarm is active
`docker swarm init` Activate swarm mode
## docker swarm init: What Just Happened?
- Lots of PKI and security automation
  - Root Signing Certificate created for our Swarm
  - Certificate is issued for first Manager node
  - Join tokens are created
- Raft database created to store root CA, configs and secrets
	- Encrypted by default on disk (1.13+)
	- No need for another key/value system to hold orchestration/secrets
	- Replicates logs amongst Managers via mutual TLS in "control plane"

`docker node ls` List nodes in swarm
`docker swarm join-token worker` Get join token for worker node

## Test Swarm
`docker service create alpine ping 8.8.8.8` Create alpine container and ping 8.8.8.8
`docker service ls` List services
`docker service ps <service_name>` List of processes (or containers) running for the given services
`docker service update <service_name> --replicas 3` Update the service to run with 3 containers
`docker container rm -f <container_name>` Try to remove the container and the orchestrator will spin it up automatically
`docker service rm <service_name>` Remove the given service