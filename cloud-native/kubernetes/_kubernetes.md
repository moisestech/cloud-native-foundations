# Kubernetes

## Kubernetes - The Container Orchestration Framework

Kubernetes - The Container Orchestrator Framework

### Summary

- So far, in this lesson, we have traversed the packaging of an application using Docker and its distribution through DockerHub.

  - The next phase in the release process is the deployment of the service.
  - However, running an application in production implies that thousands and millions of customers might consume the product at the same time.
  - For this reason, it is **paramount to build for scale**.
  - It is impossible to manually manage thousands of containers, keeping these are up to date with the latest code changes, in a healthy state, and accessible.
  - As a result, a **container orchestrator framework** is necessary.

- A container orchestrator framework is capable to create, manage, configure thousands of containers on a set of distributed servers while preserving the connectivity and reachability of these containers.

  - In the past years, multiple tools emerged within the landscape to provide these capabilities, including **Docker Swarm**, **Apache Mesos**, **CoreOS Fleet**, and many more.
  - However, Kubernetes took the lead in defining the principles of how to run containerized workloads on a distributed amount of machines.

- Kubernetes is widely adopted in the industry today, with most organizations using it in production.
- Kubernetes currently is a graduated CNCF project, which highlights its maturity and reported success from end-user companies.
- This is because Kubernetes problem solves portability, scalability, resilience, service discovery, extensibility, and operational cost of containers.

---

### Portability

- Kubernetes is a highly portable tool.
  - This is due to its open-source nature and vendor agnosticism.
  - As such, Kubernetes can be hosted on any available infrastructure, including public, private, and hybrid cloud.

### Scalability

- Building for scale is a cornerstone of any modern infrastructure, enabling an application to scale based on the amount of incoming traffic.
  - Kubernetes has in-build resources, such as HPA (Horizontal Pod Autoscaler), to determine the required amount of replicas for a service.
  - Elasticity is a core feature that is highly automated within Kubernetes.

### Resilience

- Failure is expected on any platform. However, it is more important to be able to recover from failure fast and build a set of playbooks that minimizes the downtime of an application.
  - Kubernetes uses functionalities like ReplicaSet, readiness, and liveness probes to handle most of the container failures, which enables powerful self-healing capability.

### Service Discovery

- Service discovery encapsulates the ability to automatically identify and reach new services once these are available.
  - Kubernetes provide cluster level DNS (or Domain Name System), which simplifies the accessibility of workloads within the cluster.
  - Additionally, Kubernetes provides routing and load balancing of incoming traffic, ensuring that all requests are served without application overload.

### Extensibility

- Kubernetes is a highly extensible mechanism that uses the building-block principle.
  - It has a set of basic resources that can be easily adjusted.
  - Additionally, it provides a rich API interface, that can be extended to accommodate new resources or CRDs (Custom Resource Definitions).

### Operational Cost

- Operational cost refers to the efficiency of resource consumption within a Kubernetes cluster, such as CPU and memory.
  - Kubernetes has a powerful scheduling mechanism that places an application on the node with sufficient resources to ensure the successful execution of the service.
  - As a result, most of the available infrastructure resources are allocated on-demand.
  - Additionally, it is possible to automatically scale the size of the cluster based on the current incoming traffic.
  - This capability is provisioned by the cluster-autoscaler, which guarantees that the cluster size is directly proportional to the traffic that it needs to handle.

---

## Kubernetes Architecture

Diagram of the Kubernetes architecture, composed of master and worker nodes
Kubernetes architecture, composed of control and data planes

- A Kubernetes cluster is composed of a collection of distributed physical or virtual servers.

  - These are called nodes.
  - Nodes are categorized into 2 main types: master and worker nodes.
  - The components installed on a node, determine the functionality of a node, and identifies it as a master or worker node.

- The suite of master nodes, represents the control plane, while the collection of worker nodes constructs the data plane.

---

## Control Plane

Diagram of the control plane components

Control Plane components

The control plane consists of components that make global decisions about the cluster. These components are the:

- **kube-apiserver** - the nucleus of the cluster that exposes the Kubernetes API, and handles and triggers any operations within the cluster
- **kube-scheduler** - the mechanism that places the new workloads on a node with sufficient satisfactory resource requirements
- **kube-controller-manager** - the component that handles controller processes. It ensures that the desired configuration is propagated to resources
- **etcd** - the key-value store, used for backs-up and keeping manifests for the entire cluster

There are two additional components on the control plane, they are kubelet and k-proxy. These two are special and important as they are installed on all node. You can see the Data Plane below for more details.

---

## Data Plane

Diagram of the data plane components
Data Plane components

The data plane consists of the compute used to host workloads. The components installed on a worker node are the:

- **kubelet** - the agent that runs on every node and notifies the **kube- apiserver** that this node is part of the cluster
- **kube-proxy** - a network proxy that ensures the reachability and accessibility of workloads places on this specific node

**Important Note:**

- The **kubelet** and **kube-proxy** components are installed on all the nodes in the cluster (master and worker nodes).
- These components keep the **kube-apiserver** up-to-date with a list of nodes in the cluster and manages the connectivity and reachability of the workloads.

### New terms

**CRD** - Custom Resource Definition provides the ability to extend Kubernetes API and create new resources  
**Node** - a physical or virtual server  
**Cluster** - a collection of distributed nodes that are used to manage and host workloads  
**Master node** - a node from the Kubernetes control plane, that has installed components to make global, cluster-level decisions  
**Worker node** - a node from the Kubernetes data plane, that has installed components to host workloads

---

## Quiz

1. The control plane makes the global decisions on the actions within a cluster. Which components are installed on a node to mark it as part of the control plane, but at the same time to ensure that this node is part of the Kubernetes cluster?

   - api-server
   - etcd
   - kubelet
   - kube-proxy
   - controller-manager
   - scheduler

2. The data plane is used to host workloads onto the cluster. Which components are installed on a node to mark it as part of the data plane in a Kubernetes cluster?

   - kube-proxy
   - kubelet

---

### Further Reading

Explore Kubernetes features:

[Kubernetes DNS for Services and Pods](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/)  
[Kubernetes CRDs](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)  
[Kubernete Cluster Autoscaler](https://kubernetes.io/blog/2016/07/autoscaling-in-kubernetes/)  
[Kubernetes Architecture and Components](https://kubernetes.io/docs/concepts/overview/components/)

---

## **Resources**

### **Community**

- [SUSE & Racher Community](https://community.suse.com/share/F1pMnGSvpP0S8gMl?utm_source=manual), _Community Suse_, Website

### 🎓 **Courses**

|     |     |                                                                                                                                                          |              |                            |
| --- | --- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | -------------------------- |
| 🌐  |     | [SUSE & Rancher Community Dev Workflows, and k3s](https://community.suse.com/all-courses)                                                                | **Website**  | _Rancher Community_        |
| 🌐  |     | [Getting Started with Google Kubernetes Engine](https://www.coursera.org/learn/google-kubernetes-engine)                                                 | **Website**  | _Coursera_                 |
| 🌐  |     | [Kubernetes for developers](https://www.udemy.com/share/101BQaAkYZc19WQ3w=/)                                                                             | **Website**  | _Udemy_                    |
| 🌐  |     | [Kubernetes For Container Orchestration](https://www.youtube.com/watch?v=Iz6jwltiNyY)                                                                    | **YouTube**  | _Eudereka_                 |
| 🌐  |     | [100 Days of Kubernetes](https://www.youtube.com/playlist?list=PLWnens-FYbIpUpmiiNYfkqTZQUYppGMFV)                                                       | **YouTube**  | _Anais Urlichs_            |
| 🌐  |     | [Intro to Containers w/ Docker, Kubernetes & OpenShit](https://www.coursera.org/learn/ibm-containers-docker-kubernetes-openshift)                        | **Coursera** | _IBM_                      |
| 🌐  |     | [SUSE Academy Class](https://community.suse.com/share/F1pMnGSvpP0S8gMl?utm_source=manual)                                                                | **Website**  | _Academy Classes_          |
| 🌐  |     | [Kubernetes and Docker: The Container Masterclass](https://www.packtpub.com/product/kubernetes-and-docker-the-container-masterclass-video/9781801075084) | **Website**  | _Pack_                     |
| 🌐  |     | [Lightweight Kubernetes with K3s](https://www.oreilly.com/library/view/lightweight-kubernetes-with/9781838821173/)                                       | **Website**  | _O'Reilly Online Learning_ |

### **Github**

|     |     |                                                                         |            |                   |
| --- | --- | ----------------------------------------------------------------------- | ---------- | ----------------- |
| 🌐  |     | [Microservices Basics](https://github.com/Eifel42/microservices-basics) | **GitHub** | _Eifel42_         |
| 🌐  |     | [Kubernetes The Hard Way]()                                             | **GitHub** | _KelseyHighTower_ |

### **Books**

|     |     |                                                                                                      |             |                |
| --- | --- | ---------------------------------------------------------------------------------------------------- | ----------- | -------------- |
| 🌐  |     | [Mastering Kubernetes](https://subscription.packtpub.com/book/application_development/9781788999786) | **Website** | _Pack_         |
| 🌐  |     | [The Kubernetes Handbook](https://www.freecodecamp.org/news/the-kubernetes-handbook/)                | **GitHub**  | _freeCodeCamp_ |

### 📝 **Blog Post**

|     |     |                                                                                                                                                              |             |                   |
| --- | --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------- | ----------------- |
| 🌐  |     | [Build Kubernetes-read applications on your desktop](https://www.docker.com/products/kubernetes)                                                             | **GitHub**  | _Kubernetes_      |
| 🌐  |     | [Kubernetes 101: Pods, Nodes, Containers, and Clusters](https://medium.com/google-cloud/kubernetes-101-pods-nodes-containers-and-clusters-c1509e409e16)      | **Medium**  | _Google Clouds_   |
| 🌐  |     | [MiniKube, Kubeadm, Kind, how to start with Kubernetes?](https://www.padok.fr/en/blog/minikube-kubeadm-kind-k3s)                                             | **Website** | _Padok_           |
| 🌐  |     | [Learn Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/)                                                                           | **Website** | _Kubernetes_      |
| 🌐  |     | [Pod vs Node in Kubernetes](https://medium.com/developerworld/pod-vs-node-in-kubernetes-26c858988f94)                                                        | **Medium**  | _DevWorld_        |
| 🌐  |     | [Kubernetes Tutorial: Your Complete Guide to Deploying an App on AWS with Postman](https://medium.com/better-practices/kubernetes-tutorial-b6f302a67426)     | **Medium**  | _BetterPractices_ |
| 🌐  |     | [Kubernetes 101: Pods, Nodes, Containers, and Clusters](https://medium.com/google-cloud/kubernetes-101-pods-nodes-containers-and-clusters-c1509e409e16)      | **Medium**  | _Google Cloud_    |
| 🌐  |     | [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)                                                                              | **Website** | _Kubernetes_      |
| 🌐  |     | [Cloud OnBoard: Getting Started with Google Kubernetes Engine](https://cloudonair.withgoogle.com/events/cloud-onboard-gke?utm_source=google&utm_medium=blog) | **Website** | _CloudOnAir_      |

### 🎥 Video Blogs

|     |     |                                                                                                           |             |                          |
| --- | --- | --------------------------------------------------------------------------------------------------------- | ----------- | ------------------------ |
| 🌐  |     | [MicroServices, RabbitMQ, CQRS and Event sourcing with Node](https://www.youtube.com/watch?v=XrkNwwVLyOY) | **YouTube** |                          |
| 🌐  |     | [Microservices + Events + Dockers = A Perfect Trio](https://www.youtube.com/watch?v=sSm2dRarhPo)          | **YouTube** |                          |
| 🌐  |     | [Design Patterns: Why Event Sourcing?](https://www.youtube.com/watch?v=rUDN40rdly8)                       | **YouTube** |                          |
| 🌐  |     | [Just Me & OpenSource](https://www.youtube.com/c/wenkatn-justmeandopensource/playlists)                   | **YouTube** | _Just Me and Opensource_ |

---

- [Scalable Microservices with Kubernetes](https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615)
- [Lesson 3: Container Orchestration with Kubernetes](https://www.notion.so/Lesson-3-Container-Orchestration-with-Kubernetes-671d244b4eac457ebfed73f87b63b38a#12b18cfcad754adb8ef88eb8f7a649e9)
- [Spotify – Kubernetes Podcast from Google | Podcast on Spotify](https://open.spotify.com/show/0AsnxlMtXRUEeZkIO0ScpJ?si=AIFqOIeQR3CFXUL2FKu2Gg&dl_branch=1&nd=1)
- [Lesson-3[Kubernetes] Container Orchestration with Kubernetes](https://www.notion.so/Lesson-3-Kubernetes-Container-Orchestration-with-Kubernetes-8f4fcbfc5dd242ceaaecae642a1ac0ea)
- [Notion – The all-in-one workspace for your notes, tasks, wikis, and databases.](https://www.notion.so/Lesson-4-Open-Source-PaaS-714e8f241f2f4660bb40ecac2644c25d)
- [Mastering Kubernetes - Second Edition Free eBook | Packt](https://www.packtpub.com/free-ebook/mastering-kubernetes-second-edition/9781788999786)
- [Kubernetes Cookbook - Second Edition Free eBook | Packt](https://www.packtpub.com/free-ebook/kubernetes-cookbook-second-edition/9781788837606)
- [Kubernetes Tutorial: Your Guide to Deploying an App on AWS with Postman | Postman Blog](https://blog.postman.com/kubernetes-tutorial/)
- [Kubernetes Hands-On - Deploy Microservices to the AWS Cloud | Udemy](https://www.udemy.com/course/kubernetes-microservices/)
- [Free Google Cloud Tutorial - GCVE Basics - Google Cloud VMware Engine | Udemy](https://www.udemy.com/course/gcve-basics-google-cloud-vmware-engine/?LSNPUBID=6atJFJ4NNe4)
- [Free Microservices Tutorial - Basics of Microservices | Udemy](https://www.udemy.com/course/evolution-of-microservices/?LSNPUBID=6atJFJ4NNe4)
- [Free Kubernetes Tutorial - Learn Container Orchestration- Kubernetes and Docker Swarm | Udemy](https://www.udemy.com/course/docker-swarm-kubernetes/?LSNPUBID=6atJFJ4NNe4)
- [Kubernetes Hands-On - Deploy Microservices to the AWS Cloud | Udemy](https://www.udemy.com/course/kubernetes-microservices/)
- [Kubernetes CKS 2021 Complete Course - Theory - Practice | Udemy](https://www.udemy.com/course/certified-kubernetes-security-specialist/)
- [Free Kubernetes Bootcamp - Get Prepared for the CKA & CKAD Certifications | Meetup](https://www.meetup.com/Cloud-Study-Network/events/279101055/)
- [Deployment Pipelines using GitHub Actions | A Cloud Guru](https://acloudguru.com/course/deployment-pipelines-using-github-actions)
- [Cloud Computing Certification Training Courses](https://acloudguru.com/course?type=course)
- [Introduction to Kubernetes for Beginners | A Cloud Guru](https://acloudguru.com/course/introduction-to-kubernetes)
- [Upcoming AMA with Kubernetes Instructors from Kube.academy on June 24th : kubernetes](https://www.reddit.com/r/kubernetes/comments/o1ypam/upcoming_ama_with_kubernetes_instructors_from/?mkt_tok=NjI1LUlVSi0wMDkAAAF90znsNmIcqK3gzDoU3H0GylIamqb2SjX3CpGn6jFL5JUdWhzkWmKFYmOdZlNzmrim2pBpDSutCOxP4365H0GjGwRr_T8ypGTmmfkIh5prDtpVgg)
- [Manning | Creating and Managing Cloud Native Services in Kubernetes](https://www.manning.com/liveproject/creating-and-managing-cloud-native-services-in-kubernetes?gclid=CjwKCAjw_o-HBhAsEiwANqYhp3yMBM4Y8yZDKlmGdKrkXeGNSz1OA7kgxJemf8aHbGC2Om81C4H46hoCkx0QAvD_BwE)
- [Manning | Building an ML Pipeline with Kubeflow](https://www.manning.com/liveproject/building-an-ml-pipeline-with-kubeflow)
- [Manning | Asynchronous Event Handling Using Microservices and Kafka](https://www.manning.com/liveproject/asynchronous-event-handling-using-microservices-and-kafka?query=kafka)
- [Manning | Exploring Kubernetes](https://www.manning.com/books/exploring-kubernetes)
- [Notion – The all-in-one workspace for your notes, tasks, wikis, and databases.](https://www.notion.so/REGex-Linux-Docker-Masterclass-b422f014c072470e8a3a2933f9f2e94d)
- [A Hands-On Guide for Services in Kubernetes | by Rachit Tayal | Medium](https://medium.com/@rachittayal7/a-hands-on-guide-for-services-in-kubernetes-2627acfd0b66)
- [Service Types in Kubernetes?. A Service enables network access to a… | by Kubernetes Advocate | AVM Consulting Blog | Medium](https://medium.com/avmconsulting-blog/service-types-in-kubernetes-24a1587677d6)
- [Compendium of Kubernetes Application Deployment Tools | by Karl Isenberg | Medium](https://karlkfi.medium.com/compendium-of-kubernetes-application-deployment-tools-80a828c91e8f)
- [RESTful API vs Microservice. Edit: a new great article about… | by Eric Huang | Medium](https://medium.com/@ericjwhuang/restful-api-vs-microservice-eea903ac3e73)
- [Just-in-Time Kubernetes: A Beginner’s Guide to Understanding Kubernetes Core Concepts | by Adri V | Dzero Labs | Medium](https://medium.com/dzerolabs/just-in-time-kubernetes-a-beginners-guide-to-kubernetes-core-concepts-19ee7acbafa1)
- [communications? how. Let’s talk about how microservices… | by Adnan Ahmed Khan | Medium](https://medium.com/@khanadnanxyz/communications-how-d7516a2d4e6d)
- [3 basic Kubernetes shortcuts for faster command line kung fu | by James Read | James Read’s Code, Containers and Cloud blog | Jun, 2021 | Medium](https://medium.com/james-reads-public-cloud-technology-blog/3-basic-kubernetes-shortcuts-for-faster-command-line-kung-fu-5c041295ea78)
- [Understanding kubernetes networking: pods | by Mark Betz | Google Cloud - Community | Medium](https://medium.com/google-cloud/understanding-kubernetes-networking-pods-7117dd28727)
- [Kubernetes with AKS — What and How? | by Syed Sohaib Uddin | Medium](https://medium.com/@syed.sohaib/kubernetes-with-aks-what-and-how-4f569c569909)
- [Transaction Management in Microservices (implementation guide)- part 1 | by Amir Shokri | Medium](https://amirsh71.medium.com/transaction-management-in-microservices-implementation-guide-part-1-8da3c31bfb31)
- [A Quick Tutorial on Kubernetes for Developers & Data Scientists | by narjes karmeni | The Startup | Medium](https://medium.com/swlh/a-quick-tutorial-onkubernetes-for-devlopers-cea97afa8d1c)
- [Learn Kubernetes in Under 3 Hours: A Detailed Guide to Orchestrating Containers | by Rinor Maloku | We’ve moved to freeCodeCamp.org/news | Medium](https://medium.com/free-code-camp/learn-kubernetes-in-under-3-hours-a-detailed-guide-to-orchestrating-containers-114ff420e882)
- [Top 5 Free Kubernetes Certifications | Geek Culture](https://medium.com/geekculture/top-5-free-kubernetes-certifications-8c86b2c5b590)
- [Kubernetes Endpoints. In my previous article, I defined… | by Ivan Porta | The Startup | Medium](https://medium.com/swlh/kubernetes-endpoints-2d77eca96a7b)
- [Working With ClusterIP Service Type In Kubernetes | by @pramodAIML | SysopsMicro | Medium](https://medium.com/the-programmer/working-with-clusterip-service-type-in-kubernetes-45f2c01a89c8)
- [Kubernetes Services — Part 1\. Intro to K8s services with examples | by Sandeep Baldawa | The Startup | Medium](https://medium.com/swlh/kubernetes-services-part-1-399a0dd05211)
- [The What, Why, and How of a Microservices Architecture | by Hashmap | HashmapInc | Medium](https://medium.com/hashmapinc/the-what-why-and-how-of-a-microservices-architecture-4179579423a9)
- [One CKA/CKAD/CKS requirement: Mastering Kubectl | by KumoMind | Nerd For Tech | Jul, 2021 | Medium](https://medium.com/nerd-for-tech/one-cka-ckad-cks-requirement-mastering-kubectl-85486bc0a3aa)
- [Kubernetes Best Practices. Best Practices for kubernetes are as… | by Sachin Arote | Medium](https://sachin34268.medium.com/kubernetes-best-practices-9b1435a4cb53)
- [Kubernetes and Big Data: A Gentle Introduction | by KLau | SFU Professional Master’s Program in Computer Science | Medium](https://medium.com/sfu-cspmp/kubernetes-and-big-data-a-gentle-introduction-6f32b5570770)
- [Skaffold to GKE deployment, from local to cluster. | Medium](https://abhishekx.medium.com/skaffold-to-gke-deployment-240d38ee368e)
- [Working With Services In Kubernetes | by @pramodAIML | SysopsMicro | Medium](https://medium.com/the-programmer/services-in-kubernetes-844ac2e69c6d)
- [Why Kubernetes Has Become So Popular in Data Engineering | by Anna Geller | Jun, 2021 | Better Programming](https://betterprogramming.pub/why-kubernetes-has-become-so-popular-in-data-engineering-7206b1b6d748)
- [Pizza as a Service 2.0\. Recently I was trying to describe the… | by Paul Kerrison | Medium](https://pkerrison.medium.com/pizza-as-a-service-2-0-5085cd4c365e)
- [Working with Service Account In Kubernetes | by @pramodAIML | SysopsMicro | Medium](https://medium.com/the-programmer/working-with-service-account-in-kubernetes-df129cb4d1cc)
- [Scalable and Reliable Kubernetes Logging | by Yifeng Jiang | Jun, 2021 | Medium](https://uprush.medium.com/scalable-and-reliable-kubernetes-logging-d47a27b8b04d)
- [K8s speed run, CKA, CKAS, CKA in a month | Medium](https://apaarshrm39.medium.com/k8s-speed-run-how-i-aced-ck-ad-s-in-35-days-with-a-day-occasionally-night-job-fbf60d2ebe0c)
- [Kubernetes, a practical introduction | by Fabricio Pautasso | Nexton | Medium](https://medium.com/nexton/kubernetes-a-practical-introduction-18a5b69e7763)
- [Kubernetes: Apprentice Cookbook - DEV Community](https://dev.to/aveuiller/kubernetes-apprentice-cookbook-4j6h)
- [Where does the data go? - DEV Community](https://dev.to/noviicee/where-does-the-data-go-2329)
- [Kubernetes for Dummies - DEV Community](https://dev.to/stevenmcgown/kubernetes-for-dummies-5hmh)
- [How to Become a Certified Kubernetes Application Developer](https://www.freecodecamp.org/news/how-to-become-a-certified-kubernetes-application-developer/)
- [Managing Kubernetes Objects Using Imperative Commands | Kubernetes](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-command/)
- [kubectl Cheat Sheet | Kubernetes](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Managing Kubernetes Objects Using Imperative Commands | Kubernetes](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-command/)
- [Kubernetes Components | Kubernetes](https://kubernetes.io/docs/concepts/overview/components/)
- [Autoscaling in Kubernetes | Kubernetes](https://kubernetes.io/blog/2016/07/autoscaling-in-kubernetes/)
- [kubectl Cheat Sheet | Kubernetes](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Training | Kubernetes](https://kubernetes.io/training/)
- [Kubernetes](https://kubernetes.io/)
- [Kubernetes Components | Kubernetes](https://kubernetes.io/docs/concepts/overview/components/)
- [DNS for Services and Pods | Kubernetes](https://kubernetes.io/docs/concepts/services-networking/dns-pod-service/)
- [Overview of Cloud Native Security | Kubernetes](https://kubernetes.io/docs/concepts/security/overview/)
- [Why I Use Rancher - Part One (July 2021) - YouTube](https://www.youtube.com/watch?v=g4PCTodIm80)
- [Custom Resources | Kubernetes](https://kubernetes.io/docs/concepts/extend-kubernetes/api-extension/custom-resources/)
- [Free Kubernetes Bootcamp - Get Prepared for the CKA & CKAD Certifications - YouTube](https://www.youtube.com/watch?v=PjBnj48cGg8)
- [K3s Internals: The Crazy Things We Do To Make k8s Simple - w/ Darren Shepherd, Rancher Labs - YouTube](https://www.youtube.com/watch?v=k58WnbKmjdA)
- [Kubernetes in 5 mins - YouTube](https://www.youtube.com/watch?v=PH-2FfFD2PU&ab_channel=VMwareCloudNativeApps)
- [install kuberntes : using vagrant and kubeadm - YouTube](https://www.youtube.com/watch?v=oEwrpIHjgDA)
- [Monitoring your GKE costs - YouTube](https://www.youtube.com/watch?v=lC7LSUlZ4A8)
- [Migrating From Kubernetes to Nomad & Consul at Internet Archive: 2x Pipeline Speed With GitLab - YouTube](https://www.youtube.com/watch?app=desktop&v=1n1gPMxg8bg)
- [The Illustrated Children's Guide to Kubernetes - YouTube](https://www.youtube.com/watch?v=3I9PkvZ80BQ)
- [A deeper dive into Kubernetes services - YouTube](https://www.youtube.com/watch?v=uGm_A9qRCsk)
- [Kubernetes Operator using Go! - YouTube](https://www.youtube.com/watch?v=ks7tVTxH8FM)
- [Free Kubernetes Bootcamp - Get Prepared for the CKA & CKAD Certifications - YouTube](https://www.youtube.com/watch?v=PjBnj48cGg8)
- [Free Kubernetes Bootcamp - Get Prepared for the CKA & CKAD Certifications - YouTube](https://www.youtube.com/watch?v=PjBnj48cGg8)
- [Kubernetes Best Practices and how to enforce them with Datree - YouTube](https://www.youtube.com/watch?v=hgUfH9Ab258)
- [Kubernetes Networking Intro and Deep-Dive - Bowei Du & Tim Hockin, Google - YouTube](https://www.youtube.com/watch?v=tq9ng_Nz9j8)
- [A Kubernetes story: Phippy goes to the zoo - YouTube](https://www.youtube.com/watch?v=R9-SOzep73w)
- [Kubernetes Tutorial for Beginners [FULL COURSE in 4 Hours] - YouTube](https://www.youtube.com/watch?v=X48VuDVv0do)
- [The Automation Challenge: Kubernetes Operators vs Helm Charts • Ana-Maria Mihalceanu • GOTO 2021 - YouTube](https://www.youtube.com/watch?v=dGx8PjmWkyM)
- [Kubernetes Essentials from Google Cloud - YouTube](https://www.youtube.com/playlist?list=PLIivdWyY5sqLmnGdKSdQIXq2sd_1bWSnx)
- [Kubernetes Tutorial for Beginners [FULL COURSE in 4 Hours] - YouTube](https://www.youtube.com/watch?v=X48VuDVv0do)
- [(164) Kubernetes Networking Intro and Deep-Dive - Bowei Du & Tim Hockin, Google - YouTube](https://www.youtube.com/watch?v=tq9ng_Nz9j8)
- [Example: Deploy Basic Go Application using Kubernetes - YouTube](https://www.youtube.com/watch?v=QaBnoUnSu18)
- [Debug ImagePullBackOff, and permanently remove pod using kubectl command - YouTube](https://www.youtube.com/watch?v=DKi1QBvOwqQ)
- [(159) What Is Kubernetes | Kubernetes Introduction | Kubernetes Tutorial For Beginners | Edureka - YouTube](https://www.youtube.com/watch?v=F-p_7XaEC84)
- [KUBERNETES 2021 - De NOVATO a PRO! (CURSO COMPLETO) - YouTube](https://www.youtube.com/watch?v=DCoBcpOA7W4)
- [Docker - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
- [How to Deploy a Kubernetes Cluster from Scratch - YouTube](https://www.youtube.com/watch?v=t4H6hdvB9iQ)
- [Remote - Containers - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers)
- [Kubernetes - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools)
- [Introduction to Kubernetes - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/intro-to-kubernetes/?WT.mc_id=udacity_learn-wwl)
- [Cloud Code - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=GoogleCloudTools.cloudcode)
- [Bridge to Kubernetes - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=mindaro.mindaro)
- [How to run a Kubernetes cluster on your laptop | Enable Sysadmin](https://www.redhat.com/sysadmin/kubernetes-cluster-laptop?sc_cid=7013a000003BihlAAC)
- [DZone](https://dzone.com/articles/how-to-simplify-kubernetes-application-management)
- [Kubernetes Tutorials | IBM](https://www.ibm.com/cloud/kubernetes-service/kubernetes-tutorials)
- [Use Bridge to Kubernetes to run and debug locally with Kubernetes](https://code.visualstudio.com/docs/containers/bridge-to-kubernetes)
- [Working with Kubernetes in Visual Studio Code](https://code.visualstudio.com/docs/azure/kubernetes)
- [Kubernetes by Example Homepage](https://www.kubernetesbyexample.com/en)
- [Kubernetes by Example Homepage](https://www.kubernetesbyexample.com/)
- [Courses - KubeAcademy](https://kube.academy/courses)
- [How to Manage Kubernetes With Kubectl](https://rancher.com/learning-paths/how-to-manage-kubernetes-with-kubectl/)
- [Rancher Docs: Quick-Start Guide](https://rancher.com/docs/k3s/latest/en/quick-start/)
- [Play with Kubernetes Classroom](https://training.play-with-kubernetes.com/)
- [The HackerNoon Podcast: Managing Databases on Kubernetes with Anil Kumar | Hacker Noon](https://hackernoon.com/the-hackernoon-podcast-managing-databases-on-kubernetes-with-anil-kumar-n1c377u)
- [Kubernetes Cheat Sheet | D2iQ](https://d2iq.com/resources/cheat-sheet/kubernetes-cheatsheet?utm_source=dzone&utm_medium=email&utm_campaign=21-04-12-cheatsheet-Kubernetes-Cheatsheet-update)
- [MiniKube, Kubeadm, Kind, K3S, how to start with Kubernetes?](https://www.padok.fr/en/blog/minikube-kubeadm-kind-k3s)
- [Tutorial: Install a Highly Available K3s Cluster at the Edge – The New Stack](https://thenewstack.io/tutorial-install-a-highly-available-k3s-cluster-at-the-edge/)
- [How to automate compliance and security with Kubernetes: 3 ways | The Enterprisers Project](https://enterprisersproject.com/article/2020/9/how-automate-compliance-and-security-kubernetes?sc_cid=7013a000003BihlAAC)
- [Why You Can't Talk About Microservices Without Mentioning Netflix](https://smartbear.com/blog/why-you-cant-talk-about-microservices-without-ment/)
- [The DevOps Conference of the Year | ChefConf '21: Online | Chef](https://www.chef.io/chefconf)
- [Kubernetes at the edge: easy as Pi | Ubuntu](https://ubuntu.com/engage/edge-kubernetes-raspberry-pi-webinar?utm_source=marketo&utm_medium=Email&mkt_tok=MDY2LUVPVi0zMzUAAAF9quwRGbJSl5Eaop9f0la6kZtrWerwioZ2hG-65gOLZL45OcWlMmxdhJ1D9_w_3l2rP-RUUnUBOiXd-VR7XHu3uyGzMSoRw5fuubJEkSCEIC9lLQ)
- [Summer of K8s | Ambassador Labs](https://www.getambassador.io/summer-of-k8s/)
- [Kubernetes Operators 101, Part 1: Overview and key features | Red Hat Developer](https://developers.redhat.com/articles/2021/06/11/kubernetes-operators-101-part-1-overview-and-key-features?sc_cid=7013a000002wHSXAA2)
- [Podman and Buildah for Docker users | Red Hat Developer](https://developers.redhat.com/blog/2019/02/21/podman-and-buildah-for-docker-users#what_is_buildah_and_why_would_i_use_it_)
- [Developing applications on Kubernetes | Red Hat Developer](https://developers.redhat.com/topics/kubernetes)
- [Kubernetes Patterns: Reusable Components for Designing Cloud-Native Applications | Red Hat Developer](https://developers.redhat.com/books/kubernetes-patterns/old)
- [Kubernetes Native Microservices with Quarkus and MicroProfile | Red Hat Developer](https://developers.redhat.com/books/kubernetes-native-microservices-quarkus-and-microprofile)
- [Deploy a HA K3s Cluster on DigitalOcean in 10 minutes using Terraform](https://colinwilson.uk/2021/04/04/deploy-a-ha-k3s-cluster-on-digitalocean-in-10-minutes-using-terraform/?utm_medium=email&utm_source=IaaN&utm_campaign=07012021&mkt_tok=MTEzLURUTi0yNjYAAAF-AZa953WUg80jyzowXA0hltXgnODNhQ5p5TM9QmICngaXHgacGVuwOAJOUQxwPkNck-WLhjvTN-6RpMnJh5wi3f1hbglYuRlJxrqLHxfa)
- [Eclipse Che | The Kubernetes-Native IDE for Developer Teams](https://www.eclipse.org/che/)
- [Lens | The Kubernetes IDE](https://k8slens.dev/)
- [Home - Container Journal](https://containerjournal.com/)
- [Setup Your Own Kubernetes Cluster with K3s | by Tobias Wissmueller | ITNEXT](https://itnext.io/setup-your-own-kubernetes-cluster-with-k3s-b527bf48e36a)
- [opsgenie/kubernetes-event-exporter: Export Kubernetes events to multiple destinations with routing and filtering](https://github.com/opsgenie/kubernetes-event-exporter)
- [Jumpstart your journey developing on GKE | Google Cloud Blog](https://cloud.google.com/blog/products/application-development/jumpstart-your-journey-developing-gke)
- [Test your Kubernetes experiments with an open source web interface | Opensource.com](https://opensource.com/article/21/6/chaos-mesh-kubernetes?utm_medium=Email&utm_campaign=weekly&sc_cid=7013a000002wFd2AAE)
- [https://twitter.com/k8sarchitect/status/1406297461568819212?s=21](https://twitter.com/k8sarchitect/status/1406297461568819212?s=21)
- [The Illustrated Children’s Guide to Kubernetes | Cloud Native Computing Foundation](https://www.cncf.io/the-childrens-illustrated-guide-to-kubernetes/)
- [Francesco Ciulla Blog](https://francescociulla.com/)
- [7 Free Learning Resources For Kubernetes](https://analyticsindiamag.com/7-free-learning-resources-for-kubernetes/)
- [How to avoid pitfalls when implementing microservices](https://searchapparchitecture.techtarget.com/feature/How-to-avoid-pitfalls-when-implementing-microservices?_ga=2.29091381.862366807.1623764413-1711019478.1623764413)
- [Learning Path: Kubernetes – IBM Developer](https://developer.ibm.com/components/kubernetes/series/kubernetes-learning-path/)
- [Hands-on EKS workshop for K8s security and observability | Tigera](https://www.tigera.io/event/aws-dev-day-hands-on-eks-workshop-for-k8s-security-and-observability/)
- [Stupid Simple Kubernetes: Everything You Need to Know to Start Using Kubernetes | SUSE & Rancher Community](https://community.suse.com/posts/stupid-simple-kubernetes-everything-you-need-to-know-to-start-using-kubernetes)
- [Mastering Red Hat OpenShift Applications | Free NetCom Webinar](https://www.netcomlearning.com/webinars/9794/red-hat-openshift.html?WebinarID=844&advid=1089)
- [[Free O’Reilly Ebook] Cloud Native DevOps With Kubernetes](https://www.nginx.com/resources/library/cloud-native-devops-with-kubernetes/?utm_medium=paid-social&utm_source=facebook&utm_campaign=apcj_asean-nx_pgkub&utm_content=eb-sponsoredupdate-retarget-kubs_microservices&fbclid=IwAR0rFnoDBSQSL8NkroCTpwhZisInU-s44MEJwd065Han_sLHxvCKN421q6s#download)
- [Top 8 Kubernetes Security Best Practices](https://www.magalix.com/blog/top-8-kubernetes-security-best-practices)
- [Kubernetes Essential Tools: 2021\. Review of the best tools for Kubernetes | by Javier Ramos | Jul, 2021 | ITNEXT](https://itnext.io/kubernetes-essential-tools-2021-def12e84c572)
- [Juju | Kubernetes and cloud native operations report 2021](https://juju.is/cloud-native-kubernetes-usage-report-2021)
- [How Kubernetes Services Work – BMC Software | Blogs](https://www.bmc.com/blogs/kubernetes-services/)
- [Which Is More Secure: Monolith or Microservices? | Nordic APIs |](https://nordicapis.com/which-is-more-secure-monolith-or-microservices/)
- [epinio/epinio: Opinionated platform that runs on Kubernetes, that takes you from App to URL in one step.](https://github.com/epinio/epinio)
- [Lens | The Kubernetes IDE](https://k8slens.dev/)
- [Software conformance(Certified Kubernetes) | Cloud Native Computing Foundation](https://www.cncf.io/certification/software-conformance/)
- [madhuakula/kubernetes-goat: Kubernetes Goat is "Vulnerable by Design" Kubernetes Cluster. Designed to be an intentionally vulnerable cluster environment to learn and practice Kubernetes security.](https://github.com/madhuakula/kubernetes-goat)
- [overnote/awesome-kubernetes-notes: awesome-kubernetes-notes 🎉](https://github.com/overnote/awesome-kubernetes-notes)
- [Rancher Operator: Level 1](https://community.suse.com/courses/4242073/content)
- [How do Pods communicate in Kubernetes?](https://www.tutorialworks.com/kubernetes-pod-communication/)
- [The Kubernetes Collection – Kubernetes E-Books I Microsoft Azure](https://azure.microsoft.com/en-us/resources/kubernetes-collection-host/)
- [Up and Running: K3s - May 2021](https://community.suse.com/courses/4522316/feed?autojoin=1)
- [Kubernetes Security 101: Risks and 29 Best Practices | StackRox](https://www.stackrox.com/post/2020/05/kubernetes-security-101/)
- [The Biggest Gap in Kubernetes Storage Architecture? – The New Stack](https://thenewstack.io/whats-the-biggest-gap-in-kubernetes-storage-architecture/)
- [Summer of K8s | Ambassador Labs](https://www.getambassador.io/summer-of-k8s/)
- [Containers, k8s and Istio on IBM Cloud | Free Courses in Data Science, AI, Cloud Computing, Containers, Kubernetes, Blockchain and more.](https://cognitiveclass.ai/learn/containers-k8s-and-istio-on-ibm-cloud)
- [An Ultimate Kubernetes Hands-on Labs | kubelabs](https://collabnix.github.io/kubelabs/)
- [Teleport - Access Computing Resources Anywhere](https://goteleport.com/)
- [8 Best Practices to Reduce Your AWS Bill for Kubernetes - CAST AI](https://cast.ai/blog/8-best-practices-to-reduce-your-aws-bill-for-kubernetes/)
- [KubeAcademy - Unlock your full potential with Kubernetes courses designed by experts - KubeAcademy](https://kube.academy/)
- [Hands-on workshop: Kubernetes observability design and implementation | Tigera](https://www.tigera.io/event/hands-on-workshop-kubernetes-observability-design-and-implementation-for-any-distro-any-cloud-and-any-application/?utm_campaign=laser&utm_medium=email&utm_source=marketo&mkt_tok=ODA1LUdGSC03MzIAAAF-RI0RfYT8FSsU2bmUimM-kGQV2Dx2hQy-7EMWk1hDZvtRZW2aj-_x7SaWFvfXRDjmK7w40sM7aygYeidOyQTHK1QGfP7KlEovXSv2yYox0Q)
- [knrt10/kubernetes-basicLearning: Understand kubernetes step by step. A simple repo for beginners](https://github.com/knrt10/kubernetes-basicLearning#using-#using-namespace-to-group-resources)
- [Red Hat boost automation features in Kubernetes cluster management - SiliconANGLE](https://siliconangle.com/2021/07/13/red-hat-boost-automation-features-kubernetes-cluster-management/)
- [Cloud-Native Days {with Kubernetes} 2021](https://www.mediaopsevents.com/cloudnative2021/home?_hsmi=141584922&_hsenc=p2ANqtz-_Ivbrm8hZV_OvBHq0R3mqyfYryBY2j-4JHYuRBj_dD7kDRj66Ftz4XoA5zEfJT2u6HndZSG2TUaDjxLm_PSH4NsWCL9g)
- [Architecting Kubernetes clusters — choosing the best autoscaling strategy](https://learnk8s.io/kubernetes-autoscaling-strategies)
- [Kubernetes Multi-Tenancy: Why Virtual Clusters Are The Best Solution | Loft Blog](https://loft.sh/blog/kubernetes-multi-tenancy-why-virtual-clusters-are-the-best-solution/)
- [SUSE & Rancher Community](https://community.suse.com/feed)
- [KubeAcademy Pro - KubeAcademy](https://kube.academy/pro)
- [What Is Kubernetes and What Is It Used For?](https://www.makeuseof.com/what-is-kubernetes/amp/)
- [Learning Kubernetes](https://www.linkedin.com/learning/learning-kubernetes)
- [Kubernetes vs Docker | Ubuntu](https://ubuntu.com/blog/kubernetes-versus-docker)
- [kubectl - Google Docs](https://docs.google.com/document/d/1DO-8Bjm6-5x4MTf6A7DAm9Nck8Hzv4dqEii_9-XHtpM/edit)
- [Kubernetes Podcast from Google: Episode 155 - Software Supply Chain Security, with Priya Wadhwa](https://kubernetespodcast.com/episode/155-software-supply-chain-security/)
- [Kubernetes Clusters Used to Mine Monero by Attackers – Bitcoin News](https://news.bitcoin.com/kubernetes-clusters-used-to-mine-monero-by-attackers/)
