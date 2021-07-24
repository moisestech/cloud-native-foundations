# Cloud Foundry

## Summary

Integrating PaaS solutions within an organization shifts the engineering effort from infrastructure management to product development. Additionally, it provides a powerful developer experience throughout the release process of an application, where the main functionalities are consumed through a UI or console. However, there is one major downside with this offering: vendor and application catalog lock-in. If an application is deployed using a PaaS offering from GCP, the application catalog of external services is narrowed down to GCP services mainly. Consequently, the open-source fundamentals were applied to PaaS offerings, resulting in an open-source PaaS such as **Cloud Foundry**.

Cloud Foundry is an open-source PaaS, a stand-alone software package that can be installed on any available infrastructure; private, public, or hybrid cloud. Due to its open-source nature, there is no vendor lock-in and the community can contribute to its future releases and definition of the roadmap. As such, Cloud Foundry offers a production-grade release process through a solid developer experience, that enables any application to be deployed with ease.

Note: some offerings of Cloud Foundry, can be deployed on top of Kubernetes, meaning that its main components are running as pods within a cluster.

Cloud Foundry consists of multiple components that provide these core capabilities:

- **Routing** - handle the incoming external traffic and route it to applications
- **Authentication** - identity management to user accounts
- **Application lifecycle** - controls the application deployments, monitors their status, and reconciles any new changes to reach the desired state of the application.
- **Application storage and execution** - handle the availability of artifacts to applications
- **Service** - use service brokers to provisions on-demand the dependency services for an application, such as a database or third-party APIs
- **Messaging** - ensure the communication between Cloud Foundry components
- **Metrics** and logging - aggregates the system and application metrics and logs

In the following sections, we will explore Cloud Foundry using SUSE Cloud Application Platform Developer Sandbox. However, you can explore Cloud Foundry's functionalities using the following offerings as well:

- [IBM Cloud Foundry](https://www.ibm.com/cloud/cloud-foundry)
- [SAP Cloud Platform](https://www.sap.com/products/cloud-platform/get-started.html)
- [Anynines](https://paas.anynines.com/)

---

## **Could Foundry Walkthrough - Part 1**

Let's explore the release of an application using Cloud Foundry!

**Note:** The walkthrough demos aim to highlight the simplified developer experience to release an application without the need to manage infrastructure components. Learning and understanding each Cloud Foundry functionality and implementation details is not an objective for this course.

[Udacity Video Link](https://youtu.be/-JcgNGC3cpY)

---
