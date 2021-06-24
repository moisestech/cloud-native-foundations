# Cloud App

[Course](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82)

---

## Index

1. Introduction to Cloud Native
2. CNCF and Cloud Native tooling
3. Stakeholders
4. Tools, Environment & Dependencies

---

## [Intro to Cloud-Native](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/092ac437-081d-4946-b54d-a2f537931c13/concepts/6197dd89-0c18-4bb1-998d-e7baa69aef65)

🎥 [Udacity, Video Link](https://www.youtube.com/watch?v=J3avoSaPzZ4)

- **Cloud-native** refers to the set of practices that empowers an organization to **build and manage applications at scale**.

- They can achieve this goal by using **private, hybrid, or public cloud providers**.

  - In addition to scale, an organization needs to be agile in integrating customer feedback and adapting to the surrounding technology ecosystem.

- **Containers** are associated with cloud-native terminology.
- Containers are small units of a bigger software which are isolated from each other which makes deploying them fast and resilient and they fit very well in a micro-service based architecture.
- Containers are used to run a single application with all required dependencies. The main characteristics of containers are easy to manage, deploy, and fast to recover.
- As such, often, a **micro-service-based architecture** is chosen in tandem with cloud-native tooling.
- **Micro-services** are used to manage and configure a collection of small, independent services that can be easily packaged and executed within a container.

Using multiple containers and managing them can be quite hectic so you can use am orchestrator that will help configure and deploy your containers to your cloud. There are many cloud orchestrators available some of them are.

1. Docker Swarm
2. Apache Mesos
3. Kubernetes

---

## [Cloud-Native Tooling](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/092ac437-081d-4946-b54d-a2f537931c13/concepts/79ae4fb8-2601-43f5-a879-8470d4a6c21c)

🎥 [Video Link](https://www.youtube.com/watch?v=OiwYjArTmGI)

- Overall, **Kubernetes** is a container orchestrator that is capable to problem-solve the integration of the following functionalities:

1. Runtime
2. Networking
3. Storage
4. Service Mesh
5. Logs and metrics
6. Tracing

---

## [Stakeholders](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/092ac437-081d-4946-b54d-a2f537931c13/concepts/a4eb94d3-e658-475d-bffe-04adf05e2776)

🎥 [Video Link](https://www.youtube.com/watch?v=7ZYzviRREcI)

- An engineering team can use cloud-native tooling to enable quick delivery of **value to customers** and **easily extend** to new features and technologies. These are the main reasons why an organization needs to adopt cloud-native technologies. However, when trialing cloud-native tooling, there are two main perspectives to address: business and technical stakeholders.

- From a **business perspective**, the adoption of cloud-native tooling represents:

1. **Agility** - perform strategic transformations
2. **Growth** - quickly iterate on customer feedback
3. **Service availability** - ensures the product is available to customers 24/7

- From a **technical perspective**, the adoption of cloud-native tooling represents:

1. **Automation** - release a service without human intervention
2. **Orchestration** - introduce a container orchestrator to manage thousands of services with minimal effort
3. **Observability** - ability to independently troubleshoot and debug each component

---

## [Tools, Environment & dependencies](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/092ac437-081d-4946-b54d-a2f537931c13/concepts/41d3074d-ccc2-4fc0-a153-ba7a4ba77b3b)

- [ ] [Python](https://www.python.org/downloads/)
- [ ] [Flask](https://flask.palletsprojects.com/en/2.0.x)
- [ ] [Git](https://git-scm.com/downloads)
- [ ] [Docker](https://docs.docker.com/get-docker/)
- [ ] [Vagrant](https://www.vagrantup.com/downloads)
- [ ] [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

---

## [Recap]

🎥 [Video Link](https://www.youtube.com/watch?v=1vpaXWBs6HU)

---

## Resources

## Course Notes

- [Udacity SUSE Cloud Native Scholarship Program](https://www.notion.so/Udacity-SUSE-Cloud-Native-Scholarship-Program-e42890b84701411da4b6e7b95403ce08), **Notion**, _Udacity_,

## 💻 Github

- [Udacity Cloud Native Fundamentals](https://github.com/josepraveen/Udacity_Cloud_Native_Fundamentals/tree/main/tools), **GitHub**, _JosePraveen_

## 🎓 Courses

- [IBM CLoud Native](https://cloudnative101.dev/course-overview/), **Website**, _CloudNative101_
- [Cloud Marathon](https://cloudacademy.com/promos/marathon/), **Website**, _CloudAcademy_
- [DevOps Prerequisites Course - Getting started with DevOps](https://www.youtube.com/watch?v=Wvf0mBNGjXY), **YouTube**

### 📝 Blog Post

- [What is Cloud Computing? A Beginner's Guide](https://azure.microsoft.com/en-us/overview/what-is-cloud-computing/), **Website**, _Microsoft Azure_
- [What is cloud computing? Everything you need to know](https://www.zdnet.com/article/what-is-cloud-computing-everything-you-need-to-know-about-the-cloud/), **Website**, _ZDNet_
- [2021 Upskilling Enterprise DevOps Skills Report Download](https://info.devopsinstitute.com/2021-upskilling-report-download?utm_campaign=Upskilling%202021&utm_content=167900943&utm_medium=social&utm_source=linkedin&hss_channel=lcp-6402730), **Website**, _DevOps Institute_
- [Linux Filesystem Hierarchy Explained](https://raghavaggarwal.hashnode.dev/linux-filesystem-hierarchy-explained), **Website**, _Raghav Aggarwal_
- [Everything You Need To Know About The Green Linux Lizard](https://linuxiac.com/opensuse/), **Website**, _Linuxiac_
- [What is Cloud-Native Architecture?](https://www.sdxcentral.com/cloud/cloud-native/definitions/what-is-cloud-native-architecture/), **Website**, _SdxCentral_
- [Thinking Cloud Native](https://sjoukjezaal.com/thinking-cloud-native/?utm_source=linkedin&utm_medium=social&utm_campaign=ReviveOldPost), **Website**, _Sjoukje Zaal_
- [What is the Difference Between Hyper-V and VirtualBox](https://www.diskinternals.com/vmfs-recovery/hyper-v-vs-virtualbox/), **Website**, _Diskinternals_
- [Top 10 Open Source Dev Tools](https://dev.to/budibase/top-10-open-source-development-tools-tried-and-tested-2774),**Dev.To**, _Budibase_

### 🎥 Video Blogs

- [What is Cloud Native?](https://www.youtube.com/watch?v=fp9_ubiKqFU&list=PLOspHqNVtKACSagAEeIY20NMVLNeQ1ZJx), **YouTube**, _IBM_
- [100 seconds of CI/CD DevOp Explained](https://www.youtube.com/watch?v=scEDHsr3APg), **YouTube**, _Fireship_
- [100 Seconds of ServerLess](https://youtu.be/W_VV2Fx32_Y), **YouTube**, _Fireship_
- [Cloud Native 101 Video](https://www.youtube.com/watch?v=9Ik96SBaIvs), **YouTube**, _VMware Cloud Native Apps_
- [Cloud Native DevOps Explained](https://www.youtube.com/watch?v=FzERTm_j2wE), **YouTube**, _IBM Cloud_
- <DT><A HREF="https://pages.awscloud.com/Globa_traincert_Get_AWS_Certified_Developer_Associate.html" ADD_DATE="1624502216" ICON="" >Comprehensive Cloud Skills Training Drives Digital Transformation Success</A>
- <DT><A HREF="https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615" ADD_DATE="1624502216" ICON="" >Scalable Microservices with Kubernetes</A>
- <DT><A HREF="https://github.com/josepraveen/Udacity_Cloud_Native_Fundamentals/tree/main/resources" ADD_DATE="1624502216" ICON="" >Udacity_Cloud_Native_Fundamentals/resources at main · josepraveen/Udacity_Cloud_Native_Fundamentals</A>
- <DT><A HREF="https://www.notion.so/Lesson-2-Architecture-Consideration-for-Cloud-Native-Applications-5d04e5120f8b4f90b09be446e694935d" ADD_DATE="1624502216" ICON="" >Lesson 2: Architecture Consideration for Cloud Native Applications</A>
- <DT><A HREF="https://www.tutorialbar.com/" ADD_DATE="1624502216" ICON="" >Tutorial Bar</A>
- <DT><A HREF="https://github.com/josepraveen/free_month_learning_resources/tree/main/resources" ADD_DATE="1624502216" ICON="" >free_month_learning_resources/resources at main · josepraveen/free_month_learning_resources</A>
- <DT><A HREF="https://www.packtpub.com/free-learning?utm_source=all+updates&utm_campaign=7c705a199e-packt_crm_new_freelearner_email_2&utm_medium=email&utm_term=0_c970747b22-7c705a199e-176907650&mc_cid=7c705a199e&mc_eid=926ae7a542#fl-jump?utm_source=mailchimp&utm_medium=email&utm_campaign=free_learner_onboarding" ADD_DATE="1624502216" ICON="" >Free Learning | Daily Programming eBook from Packt</A>
- <DT><A HREF="https://github.com/alexellis/k3sup" ADD_DATE="1624502216" ICON="" >alexellis/k3sup: bootstrap Kubernetes with k3s over SSH < 1 min 🚀</A>
- <DT><A HREF="https://github.com/rdotjain/cnf" ADD_DATE="1624502216" ICON="" >rdotjain/cnf</A>
- <DT><A HREF="https://awsreskill.com/signup?source=cd5e5765&medium=direct" ADD_DATE="1624502216" ICON="" >Signup - re:Skill</A>
- <DT><A HREF="https://dzone.com/articles/microservices-architecture-breaking-the-monolith?fromrel=true" ADD_DATE="1624502216" ICON="" >Microservices Architecture: Breaking the Monolith - DZone Microservices</A>
- <DT><A HREF="https://www.acm.org/" ADD_DATE="1624502216" ICON="" >Association for Computing Machinery</A>
- <DT><A HREF="https://community.suse.com/events/free-class-accelerate-dev-workflows-weeks-1-4?instance_index=20210622T160000Z" ADD_DATE="1624502216" ICON="" >Free Class: Accelerate Dev Workflows, Weeks 1-4 | Accelerate Dev Workflows - June 2021</A>
- <DT><A HREF="https://www.javatpoint.com/virtualization-in-cloud-computing" ADD_DATE="1624502216" ICON="" >Virtualization in Cloud Computing - javatpoint</A>
- <DT><A HREF="https://scrimba.com/learn/learnjavascript" ADD_DATE="1624502216" ICON="" >Learn JavaScript for free - 7-hour interactive tutorial</A>
- <DT><A HREF="https://rohankalhans.medium.com/automating-terraform-with-github-actions-5b3aac5abea7" ADD_DATE="1624502216" ICON="" >Automating Terraform with GitHub Actions | by Rohan Singh | Jun, 2021 | Medium</A>
- <DT><A HREF="https://searchapparchitecture.techtarget.com/tip/Pros-and-cons-of-monolithic-vs-microservices-architecture" ADD_DATE="1624502216" ICON="" >Pros and cons of monolithic vs. microservices architecture</A>
- <DT><A HREF="https://www.hcs-company.com/blog/containers/a-short-comparison-of-openshift-and-cloud-foundry" ADD_DATE="1624502216" ICON="" >A short comparison of OpenShift and Cloud Foundry</A>
- <DT><A HREF="https://www.youtube.com/watch?app=desktop&v=G20ugJR4Tmc" ADD_DATE="1624502216" ICON="" >The Future of Vagrant - YouTube</A>
- <DT><A HREF="https://www.udemy.com/course/vagrant-visualized-development-environments-and-oracle/?couponCode=C9B46FF62A6B35B36670" ADD_DATE="1624502216" ICON="" >Vagrant : Visualized Development Environments and Oracle | Udemy</A>
- <DT><A HREF="https://www.manning.com/books/cloud-native-applications" ADD_DATE="1624502216" ICON="" >Manning | Cloud Native Applications</A>

---

## Vocabulary

- Kubernetes
