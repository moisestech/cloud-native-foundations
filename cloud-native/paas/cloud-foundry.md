# Cloud Foundry

Cloud Foundry

Summary
Integrating PaaS solutions within an organization shifts the engineering effort from infrastructure management to product development. Additionally, it provides a powerful developer experience throughout the release process of an application, where the main functionalities are consumed through a UI or console. However, there is one major downside with this offering: vendor and application catalog lock-in. If an application is deployed using a PaaS offering from GCP, the application catalog of external services is narrowed down to GCP services mainly. Consequently, the open-source fundamentals were applied to PaaS offerings, resulting in an open-source PaaS such as Cloud Foundry.

Cloud Foundry is an open-source PaaS, a stand-alone software package that can be installed on any available infrastructure; private, public, or hybrid cloud. Due to its open-source nature, there is no vendor lock-in and the community can contribute to its future releases and definition of the roadmap. As such, Cloud Foundry offers a production-grade release process through a solid developer experience, that enables any application to be deployed with ease.

Note: some offerings of Cloud Foundry, can be deployed on top of Kubernetes, meaning that its main components are running as pods within a cluster.

Cloud Foundry consists of multiple components that provide these core capabilities:

Routing - handle the incoming external traffic and route it to applications
Authentication - identity management to user accounts
Application lifecycle - controls the application deployments, monitors their status, and reconciles any new changes to reach the desired state of the application.
Application storage and execution - handle the availability of artifacts to applications
Service - use service brokers to provisions on-demand the dependency services for an application, such as a database or third-party APIs
Messaging - ensure the communication between Cloud Foundry components
Metrics and logging - aggregates the system and application metrics and logs
In the following sections, we will explore Cloud Foundry using SUSE Cloud Application Platform Developer Sandbox. However, you can explore Cloud Foundry's functionalities using the following offerings as well:

IBM Cloud Foundry
SAP Cloud Platform
Anynines
Could Foundry Walkthrough - Part 1
Let's explore the release of an application using Cloud Foundry!

Note: The walkthrough demos aim to highlight the simplified developer experience to release an application without the need to manage infrastructure components. Learning and understanding each Cloud Foundry functionality and implementation details is not an objective for this course.

Summary
This demo showcases the main capabilities of the Stratos console and Cloud Foundry.

Some of the noteworthy sections are:

Marketplace and Services - research the service catalog and explore any integrated services
Organizations - used to manage multi-tenancy, quotas, and access to applications
Routes - list all available endpoints used to access deployed applications
Build Packs - explore available buildpacks packages used to build an application
Security groups - configure the endpoints that the application can communicate with
Could Foundry Walkthrough - Part 2
Note: This demo references the Python hello-world application.

Summary
This demo provides a step-by-step guide on how to deploy a simple Python hello-world application to Cloud Foundry.

Noteworthy steps in this demo:

Python hello-world is a simple Flask application, serving on port 8080
Cloud Foundry can use a manifest.yml file to store the configuration of the application, such as name and quotas
Routes are used to access the application and can be configured or created randomly
Further Reading
Explore Cloud Foundry and the Stratos Console in more detail:

Cloud Foundry Overview

Introduction to Stratos

Cloud Foundry: Deploying with App Manifests

Moving a Cloud Foundry Hello World App to Kubernetes - how hard can it be?

---

Quizzes: Cloud Foundry
QUESTION 1 OF 4
Why an engineering team can avoid vendor lock-in by using Cloud Foundry?

Cloud Foundry is an open-source PaaS

Cloud Foundry can be deployed on top of existing cloud providers

QUESTION 2 OF 4
Cloud Foundry offers services as part of its core functionalities. It will use service brokers to provision on-demand the dependency services for an application. What kind of dependency services does it cover?

Third-party APIs

Databases

QUESTION 3 OF 4
Which of the following sources you can use to deploy an application using Cloud Foundry?

Public GitHub repository

Docker image

Public GitLab repository

Upload source code directly

QUESTION 4 OF 4
True or False: Cloud Foundry provides routing to applications from external users.

True

---
