# Deploy Kubernetes

## Quiz

### 1. What bootstrap tools can be used to provision a production-grade Kubernetes cluster?

- [ ] Minikube
- [x] Kops
- [x] Kubeadm
- [ ] Kind
- [x] Kubespray
- [x] K3s

### Hint

- For local development, it is recommended to use **kind** and **minikube** as these are lightweight tools to provision a cluster

### 2. What are the 3 main sections of a `kubeconfig` file?

- [x] Contexts
- [x] Users
- [ ] Tokens
- [x] Clusters

### Hint

- **Contexts** are used to link a user to a cluster.
- The **Users** section contains the details of a user that wants access to the cluster.
- **Tokens** are part of the authentication metadata for a cluster.
- **Clusters** encapsulates the metadata for a cluster and how to connect to it.
