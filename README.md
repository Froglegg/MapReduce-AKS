# Kubernetes Master/Worker
> [!NOTE]
> I am not at liberty to publicly share the source code of this repository, however please reach out to me directly if you would like to discuss this project

This is a Kubernetes gRPC framework implementing a fault tolerant master / worker pattern for parallel processing at a giant scale. The Kubernetes deployment YAML files and container build scripts are configured for both local development and production deployment on cloud services such as Azure Kubernetes Service or Elastic Kubernetes Service.

This framework utilizes Etcd for distributed state management and a heartbeat mechanism for detecting slow / dead workers. In addition, Kubernetes liveness and readiness probes are used for fault tolerant, smart load balancing.


## Setup
This assumes you already have protoc, kubectl, kind, Golang, and Docker installed on your machine. Local development and testing can be done using a Kind cluster, and kubectl context can be used to run commands against a production environmnet (e.g., a cluster in AKS or EKS).

Run ./build.sh to build Golang protobuf packages, among other things. Replace placeholder registry names, secrets, etc in deployment scripts and deployment YAMLs.

## Description
This framework implements a fault tolerant master / worker pattern that utilizes etcd for managing distributed state, a heartbeat mechansism for determining worker health and task status, and Kubernetes service probes for smart load balancing.# Kubernetes-Master-Worker
