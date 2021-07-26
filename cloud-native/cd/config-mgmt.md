# Config Mgmt

## Configuration Managers

## **Summary**

- A CI/CD pipeline is essential to automate and standardize the application release process. New changes are propagated through multiple environments, including the production cluster, and ensure that the consumers can use the latest features. In an ideal situation, all clusters are similarly configured, such that the engineering team can inspect a realistic simulation of a production deployment. This implies that a set of nearly similar manifests are required for each cluster, sandbox, staging, and production. To reduce the management overhead of overseeing a similar suite configuration for each cluster, templating is necessary.

- For example, to deploy the `nginx-alpine` application 4 resource manifests were necessary: Namespace, Deployment, Service, and Configmap. However, this suite of manifests represents the deployment to a single environment, e.g sandbox. The application should be propagated through staging and production environment, which reference a separate set of manifests. It is essential to ensure that the application configuration is tailored for each environment, for example, allocate more CPU and memory to the application in production since it handles more traffic, or have a different number of replicas for each cluster. In this case, an engineering team ends up managing 3 sets of manifests, 1 for each cluster.

![Diagram showcasing the amount of manifests a team needs to manage for all enviroments]()

- A team has to manage multiple manifests, one for each enviroment, to deploy an application successfully to ptoduction

- However, the number of manifests grows exponentially when the application is distributed across multiple regions. As such, if the application is released in AP(Asia Pacific) and the US, a team ends up managing 9 different sets of manifests.

![Diagram highlighting the growing amount of manifests a team has to manage if the application is distributed across different regions]()

- Application distribution across multiple regions implies a larger number of manifests that a team should manage

- It is clear that it is necessary to introduce a mechanism to store and manage manifests in a reliable, scalable, and flexible way. This capability is offered by configuration management tools, such as:

- **Helm** - package manager that templates exiting manifests, and uses input files to tailor configuration for each environment
- **Kustomize** - a template-free mechanism that uses a base and multiple overlays, to manage the configuration for each environment
- **Jsonnet** - a programming language, that enables the templating of manifests as JSON files, that can be easily consumed by Kubernetes

- In the following sections, we will deep-dive into Helm, as the template manager of choice for this course.

---

## Helm

[Udacity, Video Link](https://youtu.be/hTBrg_1Z_FA)

## Summary 2

- **Helm** is a package manager, that manages Kubernetes manifests through charts. A Helm chart is a collection of YAML files that describe the state of multiple Kubernetes resources. These files can be parametrized using Go template.

- A Helm chart is composed of the following files:

- **Chart.yaml** - expose chart details, such as description, version, and dependencies
- **templates/ folder** - contains templates YAML manifests for Kubernetes resources
- **values.yaml** - default input configuration file for the chart. If no other values file is supplied, the parameters in this file will be used.

![Helm Chart structure including a chart configuration, input file and templated manifests]()

## Helm Chart structure

Chart.yaml
A Chart.yaml file encompasses the details of the chart, such as version, description, and maintainer list. For example, a Python hello-world Helm chart contains the following Chart.yaml configuration:

## The chart API version

apiVersion: v1

## The name of the chart.

## In this case, the chart name is`python-helloworld `.

name: python-helloworld

## A single-sentence description of this project

description: Install Python HelloWorld

## A list of keywords about this project to quickly identify the chart's capabilities.

keywords:

- python
- helloworld

## The chart version, here set to `3.7.0`

version: 3.7.0

## List of maintainers, their names, and method of contact

maintainers:

- name: kgamanji
  email: kgamanji@xyz.com
  Templates folder
  The templates/ folder is a directory containing templated YAML manifests, that require an input file to generate valid Kubernetes resources. For example, the templates/ folder contains the manifests for Deployment and Namespace resources, used to deploy the Python hello-world application:

templates/
├── deployment.yaml
└── namespace.yaml
These manifests can be templated using Go template. For example, instead of hardcoding the name of the Namespace, it can be parameterized as following:

apiVersion: v1
kind: Namespace
metadata:
name: {{ .Values.namespace.name }}
Note: The .Values object is used to access the parameters passed from the input values.yaml file.

values.yaml
The values.yaml file contains default input parameters for a Helm chart. The parameters are consumed by the templated YAML manifests through the .Values object. The end result is a suite of valid Kubernetes resources that can be successfully deployed. For example, to provide the configuration for the Deployment and Namespace resources, the values.yaml has the following structure:

## provide the name of the namespace

namespace:
name: test

## define the image to execute with the Deployment

image:
repository:
pixelpotato/python-helloworld
tag: v1.0.0

## set the number of replicas for an application

replicaCount: 3
It is noteworthy, that any fields within the Kubernetes resources can be parameterized. Additionally, the values.yaml file can be overwritten fully or partially, depending if changes are required to all parameters or just to a subset of them. If no override input file is provided, the Helm chart will fallback to using the default values.yaml file (included with the chart).

For example, to override the name of the Namespace to prod the following values-prod.yaml file can be constructed:

## override the name of the namespace

namespace:
name: prod
The end result will be a valid Kubernetes Namespace object:

apiVersion: v1
kind: Namespace
metadata:
name: prod
Argo CD and Helm

## Summary 3

- So far, we have explored how an engineering team can use **Helm charts** to template the manifests for multiple clusters.

  - The next stage consists of integrating the **Helm charts** in the deploy phase of the CI/CD pipeline.

- **ArgoCD** supports the deployment of manifests that are managed by a Helm chart. To implement this approach, the Application CRD requires to change the source of manifests to a Helm chart. An example of the manifest can be found below:

[...]
source: ## change the source of manifests to a Helm chart
helm: ## define the input values file
valueFiles: - values.yaml ## set the path to the folder where the Helm chart is stored
path: solutions/helm/python-helloworld ## set the base repository that contains the Helm chart
repoURL: https://github.com/udacity/nd064_course_1
targetRevision: HEAD
The full YAML representation of the Application CRD that deploys a Helm chart can be found in the course repository.

New Terms
Helm - package manager tool used to template a suite of Kubernetes manifests.
Helm chart - a collection of configuration, input, and templated YAML files used to deploy Kubernetes resources.

---

### Further reading

- Explore Helm configuration in more detail:

  - [The Chart Template Developer's Guide]()
  - [The Chart.yaml File]()
  - [Templates and Values]()

---

## Resources

---

## Related

- [[_cd]]
