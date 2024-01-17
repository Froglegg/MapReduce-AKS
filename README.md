# MapReduce AKS (Azure Kubernetes Service)
> [!NOTE]
> I am not at liberty to publicly share the source code of this repository, however please reach out to me directly if you would like to discuss this project and I can provide a share link.

This is a Kubernetes gRPC MapReduce framework written in Go, and which implements a fault-tolerant master / worker pattern for parallel processing at a giant scale. The Kubernetes deployment YAML files and container build scripts are configured for both local development and production deployment using Azure Kubernetes Service (AKS).

This framework utilizes Etcd for distributed state management and a heartbeat mechanism for detecting slow / dead workers. In addition, Kubernetes liveness and readiness probes are used for fault tolerant, smart load balancing. This framework also makes use of Azure Blob Storage for reading and writing intermediate files.

## Setup
This assumes you already have protoc, kubectl, kind, Golang, and Docker installed on your machine. Local development and testing can be done using a Kind cluster, and kubectl context can be used to run commands against an AKS cluster.

Run ./build.sh to build Golang protobuf packages, among other things. Replace placeholder registry names, secrets, etc in deployment scripts and deployment YAMLs.
