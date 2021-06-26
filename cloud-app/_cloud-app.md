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

| ICON  | TYPE         | Link                                                                                                                                                                                                                                                                                                                                                           |
| ----- | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 💻 ☁️ | Github       | [Udacity_Cloud_Native_Fundamentals/resources at main · josepraveen /Udacity_Cloud_Native_Fundamentals](https://github.com/josepraveen/Udacity_Cloud_Native_Fundamentals)                                                                                                                                                                                       |
| 🎓 ☸️ | Udacity      | [Scalable Microservices with Kubernetes](https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615)                                                                                                                                                                                                                                         |
| 🎓 ☁️ | AWS Cloud    | [Comprehensive Cloud Skills Training Drives Digital Transformation Success](https://pages.awscloud.com/Globa_traincert_Get_AWS_Certified_Developer_Associate.html)                                                                                                                                                                                             |
| 🌐📝  | Notion       | [Lesson 2: Architecture Consideration for Cloud Native Applications](https://www.notion.so/Lesson-2-Architecture-Consideration-for-Cloud-Native-Applications-5d04e5120f8b4f90b09be446e694935d)                                                                                                                                                                 |
| 🌐🎓  | Tutorial Bar | [Tutorial Bar](https://www.tutorialbar.com/)                                                                                                                                                                                                                                                                                                                   |
| 💻🎓  | Github       | [free_month_learning_resources/resources at main · josepraveen/free_month_learning_resources](https://github.com/josepraveen/free_month_learning_resources/tree/main/resources))                                                                                                                                                                               |
| 💻📚  | Github       | [Free Learning Daily Programming eBook from Packt](https://www.packtpub.com/free-learning?utm_source=all+updates&utm_campaign=7c705a199e-packt_crm_new_freelearner_email_2&utm_medium=email&utm_term=0_c970747b22-7c705a199e-176907650&mc_cid=7c705a199e&mc_eid=926ae7a542#fl-jump?utm_source=mailchimp&utm_medium=email&utm_campaign=free_learner_onboarding) |
| 💻☸️  | Github       | [alexellis/k3sup: bootstrap Kubernetes with k3s over SSH < 1 min 🚀](https://github.com/alexellis/k3sup)                                                                                                                                                                                                                                                       |
| 💻☸️  | Github       | [rdotjain/cnf](https://github.com/rdotjain/cnf)                                                                                                                                                                                                                                                                                                                |
| 🎓 ☁️ | AWS re:Skill | [Signup - re:Skill](https://awsreskill.com/signup?source=cd5e5765&medium=direct)cnf)                                                                                                                                                                                                                                                                           |

-
-
-
-
-
- [Microservices Architecture: Breaking the Monolith - DZone Microservices](https://dzone.com/articles/microservices-architecture-breaking-the-monolith?fromrel=true)
- [Association for Computing Machinery](https://www.acm.org/)
- [Free Class: Accelerate Dev Workflows, Weeks 1-4 | Accelerate Dev Workflows - June 2021](https://community.suse.com/events/free-class-accelerate-dev-workflows-weeks-1-4?instance_index=20210622T160000Z)
- [Virtualization in Cloud Computing - javatpoint](https://www.javatpoint.com/virtualization-in-cloud-computing)
- [Learn JavaScript for free - 7-hour interactive tutorial](https://scrimba.com/learn/learnjavascript)
- [Automating Terraform with GitHub Actions | by Rohan Singh | Jun, 2021 | Medium](https://rohankalhans.medium.com/automating-terraform-with-github-actions-5b3aac5abea7)
- [Pros and cons of monolithic vs. microservices architecture](https://searchapparchitecture.techtarget.com/tip/Pros-and-cons-of-monolithic-vs-microservices-architecture)
- [A short comparison of OpenShift and Cloud Foundry](https://www.hcs-company.com/blog/containers/a-short-comparison-of-openshift-and-cloud-foundry)
- [The Future of Vagrant - YouTube](https://www.youtube.com/watch?app=desktop&v=G20ugJR4Tmc)
- [Vagrant : Visualized Development Environments and Oracle | Udemy](https://www.udemy.com/course/vagrant-visualized-development-environments-and-oracle/?couponCode=C9B46FF62A6B35B36670)
- [Manning | Cloud Native Applications](https://www.manning.com/books/cloud-native-applications)
- [Airtable - SUSE Scholarship - Resources](https://airtable.com/shryLSJS4CQslJBO9/tbl6A99RXoOm7DYSJ)
- [Free Programming Books – GoalKicker.com](https://goalkicker.com/)
- [Developing Cloud Native Applications with Microservices Architectures | redhat.com](https://rhtapps.redhat.com/promo/course/do092?segment=11)
- [Join us for the first A Cloud Guru Community Summit | A Cloud Guru](https://get.acloudguru.com/acg-community-summit)
- [6 Essential Things You Need to Know About Cloud Native Applications](https://www.weave.works/technologies/going-cloud-native-6-essential-things-you-need-to-know/)
- [Anyscale - Ray Summit 2021](https://www.anyscale.com/ray-summit-2021?utm_source=google&utm_medium=cpc&utm_campaign=search-nam-ray&gclid=CjwKCAjwn6GGBhADEiwAruUcKuXOdyrf4WlIAb01fGzXn50R05dBd6acZYh99RwyfOzDhMY0wdL9tRoCul0QAvD_BwE)
- [Linux Foundation Launches GitOps Training - Linux Foundation - Training](https://training.linuxfoundation.org/announcements/linux-foundation-launches-gitops-training/?utm_campaign=gitops0621&utm_content=170305318&utm_medium=social&utm_source=linkedin&hss_channel=lcp-12893459)
- [free_month_learning_resources/readme.md at main · josepraveen/free_month_learning_resources]
- [Monolith Vs Microservices: Which is the Best Option for You? | Webdesigner Depot Webdesigner Depot » Blog Archive](https://www.webdesignerdepot.com/2018/05/monolith-vs-microservices-which-is-the-best-option-for-you/)
- [Hands on Lab: Introduction to Cloud Native](https://go.oracle.com/intro-cloud-native?src1=:ow:ms:pt)
- [The Complete Introduction to Data Analytics with Tableau | Udemy](https://www.udemy.com/course/the-complete-introduction-to-data-analytics-with-tableau/?ranMID=39197&ranEAID=nN98ER4vNAU&ranSiteID=nN98ER4vNAU-hvLt9X.IVxXr9kLq8BbnFw&utm_source=aff-campaign&LSNPUBID=nN98ER4vNAU&utm_medium=udemyads)
- [Linux Server Course - System Configuration and Operation - YouTube](https://www.youtube.com/watch?v=WMy3OzvBWc0)
- [Microservices vs Monolithic architecture | MuleSoft](https://www.mulesoft.com/resources/api/microservices-vs-monolithic)
- [Free Udemy Javascript Courses - Discudemy](https://www.discudemy.com/category/javascript)
- [lasalazarr/guide-monolithic-to-microservices: Step by step examples of migration phases from a Monolithic Java EE Application to Microservices](https://github.com/lasalazarr/guide-monolithic-to-microservices)
- [DevOps Engineering Course for Beginners - YouTube](https://www.youtube.com/watch?v=j5Zsa_eOXeY)
- [How to break a Monolith into Microservices](https://martinfowler.com/articles/break-monolith-into-microservices.html)
- [Make a Your Own Free VPN with AWS/Cloud Computing! | Udemy](https://www.udemy.com/course/make-a-your-own-free-vpn-with-awscloud-computing/)
- [AWS DevOps Workshop Series: Continuous Deployment](https://pages.awscloud.com/awsmp-wsm-dev-workshop-series-module3-evolving-to-continuous-deployment.html)
- [Information Technology Blogs: Continuous Integration with GitHub Action](http://blog.weetech.ch/2021/06/continuous-integration-with-github.html)
- [Find the best online Programming courses and Tutorials - Hackr.io](https://hackr.io/)
- [Microsoft Azure Tutorial - Tutorialspoint](https://www.tutorialspoint.com/microsoft_azure/index.htm)
- [SUSE & Rancher Community](https://community.suse.com/feed?autojoin=1)
- [systemd/CheatSheet - Debian Wiki](https://wiki.debian.org/systemd/CheatSheet)
- [Observability - 101 (Linux Foundation Courses/Certifications Giveaway 🔥) - YouTube](https://www.youtube.com/watch?v=bg96f0FIfT0)
- [SUSE-Cloud-Native-Foundations-Scholarship/Tools.md at main · Shivansh2407/SUSE-Cloud-Native-Foundations-Scholarship](https://github.com/Shivansh2407/SUSE-Cloud-Native-Foundations-Scholarship/blob/main/Tools.md)
- [openSUSE:Cheat sheet 13.1 - openSUSE Wiki](https://en.opensuse.org/openSUSE:Cheat_sheet_13.1#Services)
- [SUSE & Rancher Community](https://community.suse.com/feed)
- [SUSE Cloud foundations scholarship](https://www.notion.so/SUSE-Cloud-foundations-scholarship-1acf8437f5a441ca8abd1cc9cf4e3556)
- [Free Jenkins Tutorial - DevOps Crash Course: CI/CD with Jenkins Pipelines Groovy DSL | Udemy](https://www.udemy.com/course/devops-crash-course-cicd-with-jenkins-pipelines-groovy-dsl/?LSNPUBID=6atJFJ4NNe4)
- [Free Git Tutorial - MASTER Git and Github for DevOps CI/CD | Udemy](https://www.udemy.com/course/git-and-github-for-devops-ci-cd/?LSNPUBID=6atJFJ4NNe4)
- [How to Open Any Repo in VS Code Without Cloning It](https://www.freecodecamp.org/news/you-can-now-edit-anything-on-github-in-vs-code-without-cloning/)
- [Understanding cloud-native apps](https://www.redhat.com/en/topics/cloud-native-apps)
- [Linux Command Line Basics](https://www.udacity.com/course/linux-command-line-basics--ud595)
- [Free Ansible Tutorial - Ansible + GCP | Udemy](https://www.udemy.com/course/ansible-gcp/?LSNPUBID=6atJFJ4NNe4)
- [madebygps/self-taught-guide-to-cloud-computing: My self taught guide to cloud computing](https://github.com/madebygps/self-taught-guide-to-cloud-computing)
- [WSL 2: Getting started - YouTube](https://www.youtube.com/watch?v=_fntjriRe48)
- [8 books open source technologists should read this summer | Opensource.com](https://opensource.com/article/21/6/2021-opensourcecom-summer-reading-list)
- [Five open source PaaS options you should know - TechRepublic](https://www.techrepublic.com/article/five-open-source-paas-options-you-should-know/)

---

## Vocabulary

- Kubernetes
