# CD Fundamentals

[Udacity Video Link](https://www.youtube.com/watch?v=OSg1NXhQoXk)

## **Summary**

- Once an engineering team has automated the packaging of an application, the next phase is to release it to customers.
  - Before the application is pushed to a production environment, it is important to check the functionality of an application when deployed and integrated with platform components.
  - Only when the application meets the excepted behavior, it is deployed to a customer-facing environment.
  - The process of propagating an application through multiple environments, until it reached the end-users, is known as the **Continuous Delivery** (or CD) stage.

![](../../assets/images/lessons/L5_9_cd_fundamentals_vid_1.png)

- It is common practice to push the code through at least 3 environments: sandbox, staging, and production.

  - A reminder of each environment's purpose :

- **Sandbox** - development environment, where new changes can be tested with minimal risk.
- **Staging** - an environment identical to production, and where a release can be simulated without affecting the end-user experience.
- **Production** - customer-facing environment and any changes in this environment will affect the customer experience.

- The sandbox and staging environments are fully automated.
  - As such, if the deployment to sandbox is successful and meets the expected behavior, then the code will be propagated to the staging automatically.
  - However, the push to production requires engineering validation and triggering, as this is the environment that the end-users will interact with.
  - The production deployment can be fully automated, however, doing so implies a high confidence rate that the code will not introduce customer-facing disruptions.

![Diagram of Continuous Delivery stages](../../assets/images/lessons/L5_9_cd_fundamentals_vid_2.png)

![](../../assets/images/lessons/L5_9_cd_fundamentals_vid_3.png)

- **Continuous Delivery stages**

- Within the deployment pipeline, Continuous Delivery covers the **deploy** stage.

  - Throughout this course, we have practiced the deployment of an application while using kubectl commands.

- **Kubernetes CLI (kubectl)**, support the management of imperative and declarative configuration.
  - With the imperative approach, a Python hello-world application is deployed by creating a Deployment resource and referencing the desired Docker image:

---

```bash python
# deploy `python-helloworld` using the imperative approach
kubectl create deploy python-helloworld --image=pixelpotato/python-helloworld:v1.0.0
```

- On the other side, with the declarative approach, the Python hello-world Deployment is store in a YAML manifest and is created using the `kubectl apply` command:

```bash python
# deploy `python-helloworld` using the declarative approach
kubectl apply -f deployment.yaml
```

- **Note:** The declarative approach is the recommended way to deploy resources within a production environment. Hence, this configuration management technique will be referenced in the next sections.

---

## Argo CD

[Udacity Video Link](https://youtu.be/rHUeSniRVUk)

![Argo CD Advantages]()

![Argo CD Info](../../assets/images/lessons/lesson_1_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_2_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_3_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_4_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_5_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_6_icon.jpeg)
![Argo CD Info](../../assets/images/lessons/lesson_7_icon.jpeg)

### **Summary 2**

- The ecosystem is rich in the collection of tools that automate the Continuous Delivery stage, such as
  - Jenkins
  - CircleCI
  - Concourse
  - Spinnaker
- However, in this lesson, we will explore ArgoCD to propagate an application to multiple Kubernetes clusters.

- **ArgoCD** is a declarative Continuous Delivery tool for Kubernetes, which follows the GitOps patterns.

  - As such, **ArgoCD** operates on configuration stored in manifests (declarative) and uses Git repositories as the source of truth for the desired state of an application (GitOps pattern).
  - As such, **ArgoCD** monitors the new commits to Git repositories and applies the latest changes reconciled automatically or on a manual trigger.
  - Additionally, **ArgoCD** offers deployment to target environments and multiple clusters, and support for multiple config management tools (such as **plain YAML, Helm, Kustomize**).

- For application deployment through multiple environments, **ArgoCD** provides CRDs (Custom Resource Definitions) to configure and manage the application release.

### **Project resource**

- The **Project** resource is a CRD that provides a logical grouping of applications, including access to source and destination repositories, and permissions to resources within the cluster.
  - This resource is handy to segregate and control the deployment to multiple clusters.

### **Application resource**

- The **Application** resource that stores the configuration of how an application should be deployed and managed.
- Let's explore how a Python hello-world application is deployed using an ArgoCD Application resource:
- _Note:_ It is assumed that the declarative manifests for Python hello-world are available ((**e.g. deploy.yaml, service.yaml**, etc).

```bash
## API endpoint used to create the Application resource
apiVersion: argoproj.io/v1alpha1
kind: Application

## Set the name of the resource and namespace where it should be deployed.
## In this case the Application resource name is set to `python-helloworld `
## and it is deployed in the `argocd` namespace
metadata:
name: python-helloworld
namespace: argocd
spec:
## Set the target cluster and namespace to deploy the Python hello-world application.
## For example, the Python hello-world application is deployed in the `default` namespace
## within the local cluster or `https://kubernetes.default.svc`
destination:
namespace: default
server: https://kubernetes.default.svc
## Set the project the application belongs to.
## In this case the `default` project is used.
project: default
## Define the source of the Python hello-world application manifests.
## In this example, the manifests are stored in the `argocd-demo` repository
## under the `python-manifests` folder. Additionally, the latest commit within
## the repository is targeted or `HEAD`.
source:
path: python-manifests
repoURL:
https://github.com/kgamanji/argocd-demo
targetRevision: HEAD
# # Set the sync policy.
## If left empty, the sync policy will default to manual.
syncPolicy: {}
```

---

![App of Apps](./../../assets/images/lessons/L5_9_cd_fundamentals_app_of_apps.png)

- Diagram of a web-store Application that manages the configuration multiple microservices

- App of Apps: manage the Application CRDs for multiple microservices with a single Application CRD

- **ArgoCD** provides an ???app-of-apps??? technique that enables a group of applications to be deployed and configured together.
  - This technique is useful if a product is developed using a microservice-based architecture, and a single point of orchestration is necessary to deploy all microservices.
  - For example, a Web-store Application CRD can be used to manage the Application CRDs for the UI, Login, and Payment units.
  - In this case, one point of control is provisioned to release and manage multiple microservices.

### New Terms

- **GitOps** - an operating model that refers to the Git repositories as the source of truth for declarative infrastructure and applications.

### Further Reading

- Explore the GitOps pattern and ArgoCD resources:

- [A Guide To GitOps](https://www.weave.works/technologies/gitops/)
- [ArgoCD Project CRD](https://argoproj.github.io/argo-cd/operator-manual/declarative-setup/#projects)
- [ArgoCD Application CRD](https://argoproj.github.io/argo-cd/operator-manual/declarative-setup/#applications)

---

## Jenkins Resources

- [Jenkins Cheat Sheet](https://lzone.de/cheat-sheet/Jenkins)
- [Online Courses - Anytime, Anywhere | Udemy](https://www.udemy.com/cart/subscribecourse/2780262/)
- [Free Jenkins Tutorial - DevOps Crash Course: CI/CD with Jenkins Pipelines Groovy DSL| Udemy](https://www.udemy.com/course/devops-crash-course-cicd-with-jenkins-pipelines-groovy-dsl/?LSNPUBID=6atJFJ4NNe4)
- [7 Best Courses to learn Jenkins and CI/CD for DevOps Engineers and SoftwareDevelopers in 2021 | by javinpaul | Javarevisited | Medium](https://medium.com/javarevisited/7-best-courses-to-learn-jenkins-and-ci-cd-for-devops-engineers-and-software-developers-df2de8fe38f3)
- [New eBook: Jenkins is the Way for IT and software developers](https://www.jenkins.ioblog/2021/06/10/jenkins-is-the-way-ebook-2/)
- [Complete end-to end Automation integrating Docker, Github with Jenkins CI/CD | byAnkush Sinha Roy | Medium](https://medium.com/@srank2000/complete-end-to-end-automation-integrating-docker-github-with-jenkins-ci-cd-b555e721aad4)

## **Related**
