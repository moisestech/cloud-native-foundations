# CD

## Continuous Deployment

### Summary

- Throughout the Microservice Fundamentals course, we walked through a realistic example of how to choose an architecture for an application, package it using Docker, and deployed it to a Kubernetes cluster using a CI/CD pipeline.

  - We have started off with an overview of the cloud-native ecosystem and the tools it hosts. Then we've learned different application designs, such as monoliths and microservice, and implied trade-offs.
  - We then moved to package an application using Docker and deploy it to a Kubernetes cluster using imperative and declarative configurations.
  - Then, we transitioned into Platform as a Service (or PaaS) solutions and explored Cloud.

- Foundry as an approach to deploy an application without worrying about the underlying infrastructure.

  - And we finished this course, by practicing cloud-native tooling to construct a CI/CD pipeline.
  - We deep-dived into GitHub Actions and ArgoCD and explored template configuration managers, such as Helm.
  - Overall, in this course we have covered the following lessons:•Welcome•Architecture Considerations•Container Orchestration•Open Source PaaS Cloud Native CI/CD

- [ND064 C1 L4 13 Course Recap](https://www.youtube.com/watch?v=rb4BOakWoe4&feature=emb_imp_woyt)
- [ND064 C1 L4 14 Goodbye](https://www.youtube.com/watch?v=NabhBOKXn5Y&feature=emb_imp_woyt)

### Application Releases

![](../../assets/images/lessons/udacity_cnf_lesson_5_cicd_app_release_1.png)

- Automation of the release process is fundamental
- This module will focus on building a delivery pipeline to deploy to a Kubernetes cluster to completely automate the process using cloud native tooling

![](../../assets/images/lessons/udacity_cnf_lesson_5_cicd_app_release_2.png)

- Up to this stage, we have practiced the packaging of an application using Docker and its deployment to a Kubernetes cluster using kubectl commands.

  - As well, we have explored the simplified developer experience of application release with Cloud Foundry. However, in both cases, a user has to manually trigger and complete all the operations.
  - This is not sustainable if tens and hundreds of releases are performed within a day.
  - Automation of the release process is fundamental!In the case of a PaaS offering, the release of a new feature is managed by the provider.
  - For example, Cloud Foundry monitors the repository with the source code, and when a new commit is identified, the user can easily deploy the latest changes with a click of a button.
  - On the other side, releasing an application to a Kubernetes cluster consists of a series of manually typed docker and kubectl commands.
  - At this stage, this approach has no automation integrated.
  - In this lesson, we will not cover how a PaaS automates the release process, since this is already solutionized by the 3rd party providers. Instead, we will focus on building a delivery pipeline to automate the deployment to Kubernetes using cloud-native tooling.

- [Udacity, Video Link, **ND064 L4 02 Big Picture**](https://youtu.be/D0WMUP5qMYM)

---

## Continouos Application Deployment

[**Udacity, Video Link, Continuous Application Deployment**, _ND064 C1 L4 03_](https://www.youtube.com/watch?v=p_hVoLkTDp8)

- Every company has the same goal: to deliver value to customers and maintain customer satisfaction.

  - To achieve this, an organization needs to be fast in integrating customer feedback and release new features.
  - It is possible to manually deploy every release for a small product.
  - However, this is not viable for a product that has thousands of microservices developed by hundreds of engineers.
  - A delivery pipeline is essential for continuous and automated deployment of new functionalities.
  - A delivery pipeline includes stages that can test, validate, package, and push new features to a production environment.
  - It is common practice for the main branch commits to proceed through all stages of the pipeline to reach the end-users.
  - Overall, a delivery pipeline is triggered when a new commit is available.
  - The new changes should traverse the following stages:
    - •Build - compile the application source code and its dependencies.
    - If this stage fails the developer should address it immediately as there might be missing dependencies or errors in the code
    - Test - run a suite of tests, such as unit testing, integration,

- UI, smoke, or security tests. These tests aim to validate the behavior of the code.
  - If this stage fails, then developers must correct it to prevent dysfunctional code from reaching the end-users.
  - Package - create an executable that contains the latest code and its dependencies.
  - This is a runnable instance of the application that can be deployed to end-users.
  - Deploy - push the packaged application to one or more environments, such as sandbox, staging, and production.
  - Usually, the sandbox and staging deployments are automatic, and the production deployment requires engineering validation and triggering.
  - It is common practice to push an application through multiple environments before it reaches the end-users.
  - Usually, these are categorized as follows:•Sandbox - development environment, where new changes can be tested with minimal risk
  - Staging - an environment identical to production, and where a release can be simulated without affecting the end-user experience
  - Production - customer-facing environment and any changes in this environment will affect the customer experience.

![](../../assets/images/lessons/udacity_cnf_lesson_5_cicd_cont_deploy_1.png)

- Overall, a delivery pipeline consists of two phases:
  - **Continuous Integration (or CI)** includes the build, test, and package stages.•Continuous Delivery (or CD) handles the deploy stage
  - **Advantages of a CI/CD pipeline**
    - **Frequent releases** - automation enables engineers to ship new code as soon as it's available and improves responsiveness to customer feedback.
    - **Less risk** - automation of releases eliminates the need for manual intervention and configuration.
    - **Developer productivity** - a structured release process allows every product to be released independently of other componentsNew Terms
  - **Continuous Integration** - a mechanism that produces the package of an application that can be deployed.•Continuous Delivery - a mechanism to push the packaged application through multiple environments, including production.
  - **Continuous Deployment** - a procedure that contains the Continuous Integration and Continuous Delivery of a product.

### Further Reading

- [CI/CD: Continuous Integration & Delivery Explained](https://semaphoreci.com/cicd)
- [What’s the Difference Between Continuous Integration, Continuous Deployment and Continuous Delivery?](https://semaphoreci.com/blog/2017/07/27/what-is-the-difference-between-continuous-integration-continuous-deployment-and-continuous-delivery.html)

---

### CI/CD Resources

- [(3433) GitHub Actions Tutorial - Basic Concepts and CI/CD Pipeline with Docker - YouTube](https://www.youtube.com/watch?v=R8_veQiYBjI)
- [(5219) GitHub Actions Tutorial - Basic Concepts and CI/CD Pipeline with Docker - YouTube](https://www.youtube.com/watch?v=R8_veQiYBjI)
- [Build a complete CI/CD Pipeline and its infrastructure with AWS — Jenkins — Bitbucket — Docker — Terraform → Part 3 | by Kevin De Notariis | Jun, 2021 | FAUN](https://faun.pub/build-a-complete-ci-cd-pipeline-and-its-infrastructure-with-aws-jenkins-bitbucket-docker-22c49ad4674a)
- [Using Grafana to visualize Continuous Delivery Indicators in the open source Jenkins X cloud native CI/CD project | Grafana Labs](https://grafana.com/go/grafanaconline/2021/jenkinsx-grafana/)
- [Lesser Known Techniques for Attacking AWS Environments - tl;dr sec](https://tldrsec.com/blog/lesser-known-aws-attacks/)
- [Configure GitHub Actions | Docker Documentation](https://docs.docker.com/ci-cd/github-actions/)
- [Leveraging GitOps to Automate the Delivery of Code and Infrastructure | SUSE & Rancher Community](https://community.suse.com/posts/15181795?utm_source=manual)
- [(165) Let's Learn Epinio - YouTube](https://www.youtube.com/watch?v=ietNQSQXhAc)
- [(165) 127.0.0.1 vs 0.0.0.0 (Simple Explanation) - YouTube](https://www.youtube.com/watch?v=my2vBYZ1RFw)
- [GitHub Actions with built-in CI/CD comparing v1 & v2\. | Lothar Schulz](https://www.lotharschulz.info/2019/08/26/ci-cd-with-github-actions-v2/)
- [Automating Developer Things with GitHub Action - Brian Douglas - YouTube](https://www.youtube.com/watch?v=jnpVn6jTKYM)
- [(3217) The Monthly Dev #6: Special Edition with Microsoft Reactor & GitHub (June 2021) - YouTube](https://www.youtube.com/watch?v=ufEjbVpaqc4)
- [CI/CD Tutorials - YouTube](https://www.youtube.com/playlist?list=PLy7NrYWoggjzSIlwxeBbcgfAdYoxCIrM2)
- [Deployment Pipelines using GitHub Actions | A Cloud Guru](https://acloudguru.com/course/deployment-pipelines-using-github-actions)
- [Code House - Store House of 300+ Developer Cheatsheets](https://codehouse.vercel.app/)
- [CI/CD - Wikipedia](https://en.m.wikipedia.org/wiki/CI/CD)
- [Introduction to GitHub Actions](https://www.telerik.com/blogs/introduction-github-actions)
- [cdCon 2021 - YouTube](https://www.youtube.com/playlist?list=PL2KXbZ9-EY9TWsV-Jz8ARSt1ko0Yd36ah)
- [Continuous integration vs. continuous delivery vs. continuous deployment](https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment)
- [8 Security Considerations for CI/CD - DevOps.com](https://devops.com/8-security-considerations-for-ci-cd/amp/)
- [CI/CD Tutorials - YouTube](https://www.youtube.com/playlist?list=PLy7NrYWoggjzSIlwxeBbcgfAdYoxCIrM2)
- [Pulumi GitHub Actions | Pulumi](https://www.pulumi.com/docs/guides/continuous-delivery/github-actions/)
- [CI/CD: Continuous Integration & Delivery Explained - Semaphore](https://semaphoreci.com/cicd)
- [What's the Difference Between Continuous Integration, Continuous Deployment and Continuous Delivery? - Semaphore](https://semaphoreci.com/blog/2017/07/27/what-is-the-difference-between-continuous-integration-continuous-deployment-and-continuous-delivery.html)

## Related Foam Links

- [[README]]
- [[argocd]]
- [[cd-fundamentals]]
- [[helm]]
- [[edge-case]]
