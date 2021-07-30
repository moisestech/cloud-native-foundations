# Helm

## Helm Walkthrough

- This demo provides a step-by-step guide on how to create a Helm chart to deploy the Python hello-world application.
- Additionally, this demo showcases how ArgoCD is used to deploy the Python hello-world Helm chart using the default and prod input values files.

- To follow this demo closely, reference these resources:

- **Python hello-world** Helm chart that is used to parameterized the Namespace and Deployment resources. Note how the values.yaml and values-prod.yaml files are used to overwrite name of the Namespace.
- The Application CRD to deploy the Helm chart referencing the default input values file, can be found in argocd-helm-python.yaml manifest
- The Application CRD used to deploy the Helm chart referencing the values-prod.yaml file, can be found in argocd-helm-python-prod.yaml manifest

- [Udacity Video Link](https://youtu.be/i1ZvdS7qdAI)

---

### Exercise: Configuration Managers

- For the management of multiple declarative Kubernetes manifests, a templating layer is necessary, especially if the application is replicated across different regions.

  - For this purpose configuration managers, such as Helm and Kustomize, were introduced.

- This exercise will focus on creating your first Helm chart to deploy multiple Nginx applications using the same template and multiple input files.

---

### Exercise

Using the manifests provided in the course repository, create a helm chart (Chart.yaml, templates, values.yaml) that will template the following parameters:

namespace name
replica count
image:
name
tag
pull policy
resources
requests for CPU and memory
service
port
type (e.g. ClusterIP)
configmap data (e.g. the key-value pair)
The chart details should be as following:

name: nginx-deployment
version: 1.0.0
keywords: nginx
Once the Helm chart is available make sure that a default values.yaml file is available. This values file will be used as a default input file for the Helm chart. The values.yaml file should have the following specification:

values.yaml
namespace name: demo
replica count: 3
image repository: nginx
image tag: alpine
image pull policy: IfNotPresent
resources: CPU 50m and memory 256Mi
service type: ClusterIP
service port: 8111
configmap data: "version: alpine"
Next, create 2 values files with the following specifications:

values-staging.yaml

namespace name: staging
replica count: 1
image repository: nginx
image tag: 1.18.0
resources: CPU 50m and memory 128Mi
configmap data: "version: 1.18.0"
values-prod.yaml

namespace name: prod
replica count: 2
image repository: nginx
image tag: 1.17.0
resources: CPU 70m and memory 256Mi
service port: 80
configmap data: "version: 1.17.0"
Finally, using the values files above (values-prod, values-staging), create 2 ArgoCD application, nginx-staging and nginx-prod respectively. These should deploy the nginx Helm Chart referencing each input values files.

Make sure you completed the following tasks:

---

## Solution: Configutation Managers

### Create Helm Chart

- Helm provides a powerful mechanism to inject values to templated YAML manifests.

- The full Helm chart for nginx-deployment can found in the course repository.

- The Helm chart is defined in the Chart.yaml file, which contains the API version, name and version of the chart:

apiVersion: v1
name: nginx-deployment
description: Install Nginx deployment manifests
keywords:

- nginx
  version: 1.0.0
  maintainers:
- name: kgamanji
  An example of the values.yaml file can be found below:

namespace:
name: demo

service:
port: 8111
type: ClusterIP

image:
repository: nginx
tag: alpine
pullPolicy: IfNotPresent

replicaCount: 3

resources:
requests:
cpu: 50m
memory: 256Mi

configmap:
data: "version: alpine"
The above configuration represents the default parameters of application deployment if it is not overwritten by a different values file.

- Below is an example of the values-prod.yaml file, which will override the default parameters:

namespace:
name: prod

service:
port: 80
type: ClusterIP

image:
repository: nginx
tag: 1.17.0
pullPolicy: IfNotPresent

replicaCount: 2

resources:
requests:
cpu: 70m
memory: 256Mi

configmap:
data: "version: 1.17.0"
The values-staging.yaml can be found in the course repository.

Deploy Helm Chart

And finally, here is ArgoCD application CRD for the nginx-prod deployment:

apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
name: nginx-prod
namespace: argocd
spec:
destination:
namespace: default
server: https://kubernetes.default.svc
project: default
source:
helm:
valueFiles: - values-prod.yaml
path: helm
repoURL: https://github.com/kgamanji/argocd-demo
targetRevision: HEAD
The nginx-staging.yaml Application for ArgoCD can be found in the course repository.

---

## Helm Resources

- [10 Helm Tutorials to Start your Kubernetes Journey | JFrog](https://jfrog.com/blog/10-helm-tutorials-to-start-your-kubernetes-journey/)
- [Setting up a private Helm chart repository on GitHub | by Jasiek Petryk | Medium](https://jasiek-petryk.medium.com/setting-up-a-private-helm-chart-repository-on-github-4a767703cec8)
- [Application and package management using Helm - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/aks-app-package-management-using-helm/?WT.mc_id=udacity_learn-wwl)
- [13 Best Practices for using Helm — Coder Society](https://codersociety.com/blog/articles/helm-best-practices)

### Related

- [[_cd]]
