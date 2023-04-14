# Kubernetes Study

Container orchestration tool focused on high availability, scalability and disaster recovery.

## Architecture

A Kubernetes cluster contains a set of worker machines, called nodes
- **Control Plane**: works as a master node and controls the worker nodes
- **Worker nodes**: host the containerized applications in Pods. Each node can have 1 to N pods (containers)

![](https://d33wubrfki0l68.cloudfront.net/2475489eaf20163ec0f54ddc1d92aa8d4c87c96b/e7c81/images/docs/components-of-kubernetes.svg)

### Control Plane Components

- API Server: Entrypoint to k8s cluster (CLI, UI, API)
- Controller Manager: Tracks what's happening
- Scheduler: Decides which node an new pod should run based on resources requirements
- ETCD: Store key/value configs and values, like the current status of any component

### Worker Nodes Components

- Kubelet: A agent that runs on each node
- Kube-proxy: A network proxy that runs on each node
- Container runtime: Runs containerized applications

## Virtual Network

Creates one unified machine along the cluster.

## Main Components

### Pod

- Smallest part/unit
- Abstraction over containers
- Runs one application only
- Each Pod has one IP address
- It's ephemeral
- New IP on every recreation

### Service

- Permanent IP address
- Lifecycle with Pod isn't connected
- Type: ExternalService or InternalService
- One service per Pod
- Works as a loadbalancer for it's many Pods

### Ingress

- Route traffic into cluster

### Config-map

- Key/value not confidential pairs, like settings or connection strings

### Secret

- Sensitive data, stored in base64

### Volumes

- Storage not ephemeral
- Could be used inside or outside the cluster
- **k8s doesn't manage data persitence**

### Deployment

- Blueprint for abstractions over Pods
- **Always work with Deployments, not Pods**

### StatefulSet

- For databases of stateful apps