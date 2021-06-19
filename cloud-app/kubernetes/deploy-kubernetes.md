# Deploy Kubernetes

## [Quiz](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/acbe666f-c1e1-44b5-b914-eedb30c2542c)

### 1. What bootstrap tools can be used to provision a production-grade Kubernetes cluster?

- [ ] Minikube
- [x] Kops
- [x] Kubeadm
- [ ] Kind
- [x] Kubespray
- [x] K3s

#### Hint Question 1

- For local development, it is recommended to use **kind** and **minikube** as these are lightweight tools to provision a cluster

### 2. What are the 3 main sections of a `kubeconfig` file?

- [x] Contexts
- [x] Users
- [ ] Tokens
- [x] Clusters

#### Hint Question 2

- **Contexts** are used to link a user to a cluster.
- The **Users** section contains the details of a user that wants access to the cluster.
- **Tokens** are part of the authentication metadata for a cluster.
- **Clusters** encapsulates the metadata for a cluster and how to connect to it.

---

## Exercise: Deploy Your First Kubernetes Cluster

**Environment Setup** - Provision a Vagrant box locally and install Kubernetes with k3s.

**Note:** Make sure to have VirtualBox 6.1.16 or higher installed .

### Task List

[ ] Install vagrant on your machines
[ ] Clone the course repository using git Commands
[ ] Navigate inside the `exercises` directory and examine the `Vagrantfile`
[ ] Create a vagrant box by using `vagrant up` command (Note: you need to be in the same repository as the Vagrant file for this command to work)
[ ] SSH into the vagrant box by using `vagrant ssh` command
[ ] Deploy a Kubernetes cluster using [K3s](https://k3s.io/)
[ ] Examine your cluster using `kubectl` command (Note: you need to be root access the kubeconfig file, use `sudo su -` before the kubectl commands)

---

## Exercise: Writing Questions

Now you should have a Kubernetes cluster up and running. Examine the cluster and identity of the following details.

Use the blank space to record your answer if necessary,

### Question 1

Reflect
From the kubeconfig, identify:

1. the IP and port of the API server
2. authentication mechanism

**Note:** Refer to the main [k3s installation guide](https://rancher.com/docs/k3s/latest/en/quick-start/#install-script), to find the location of the kubeconfig file.

### Question 2

Reflect
From the cluster using kubectl commands to identify:

- endpoints of the control plane and add-ons
- amount of nodes
- node internal IP
- the pod CIDR allocate to the node

**Note:** To access kubectl commands you need to become root by using sudo su - command.

---

## [Solutions](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/4afbeb16-941b-4baf-a472-c292d06621ea)

The kubeconfig file and kubectl commands are the 2 main components that permits the interaction with a Kubernetes cluster.

Let's take a closer look at cluster configuration details.

### kubeconfig

- **K3s** stores the kubeconfig file under <code>/etc/rancher/k3s/k3s.yaml</code> path
- **API server** - <code>https://127.0.0.1:6443</code>
- **authentication mechanism** - username (admin) and password

### kubectl commands

<code>kubectl cluster-info</code> to get the control plane and add-ons Endpoints

<pre><code class="lang-bash">Kubernetes master is running at https://127.0.0.1:6443
CoreDNS is running at https://127.0.0.1:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
Metrics-server is running at https://127.0.0.1:6443/api/v1/namespaces/kube-system/services/https:metrics-server:/proxy
</code></pre>

<code>kubectl get nodes</code> - to get all the nodes in the Cluster

<pre><code class="lang-bash">NAME        STATUS   ROLES    AGE   VERSION
localhost   Ready    master   74m   v1.18.9+k3s1
</code></pre>

<code>kubectl get nodes -o wide</code> - to get extra details about the nodes, including internal IP

<pre><code class="lang-bash">NAME        STATUS   ROLES    AGE   VERSION        INTERNAL-IP   EXTERNAL-IP   OS-IMAGE             KERNEL-VERSION            CONTAINER-RUNTIME
localhost   Ready    master   74m   v1.18.9+k3s1   10.0.2.15     &lt;none&gt;        openSUSE Leap 15.2   5.3.18-lp152.47-default   containerd://1.3.3-k3s2
</code></pre>

<code>kubectl describe node node-name</code> - to get all the configuration details about the node, including the allocated pod CIDR

<pre><code class="lang-bash">kubectl describe node localhost | grep CIDR
PodCIDR:                      10.42.0.0/24
PodCIDRs:                     10.42.0.0/24
</code></pre>
