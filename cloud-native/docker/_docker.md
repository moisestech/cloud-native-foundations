# Docker

- A tool that can package software into container that work reliably on any environment.
- Instead of virtualizing the hardware, containers only virtualize the OS (Operating System)
- All apps and containers are ran by a single kernel

---

## [What is a Container?](https://www.docker.com/resources/what-container)

- A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.

## 3 Elements of a Docker

1. **Docker File**
   - It's like DNA, it is code that tells Docker how to build an image.
2. **Image**
   - A snapshot of your software with all of its dependencies down to its operating system level.
   - The image is immutable which can be used to spin up multiple containers which is the actual software running in the real world.
3. **Container**
   - Actual Software running in the real world.

---

## Docker for Application Packaging

| DOCKER COMPONENT     | PURPOSE                                                  |
| -------------------- | -------------------------------------------------------- |
| **Docker File**      | Set of instructions to create a Docker Image             |
| **Docker Image**     | A read-only template that is used to spin-up a container |
| **Docker Container** | A runnable instance of the Docker image                  |
| **Docker Registry**  | A tool used to store and distribute Docker images        |

By default, Docker will create OCI (Open Container Initiative) compliant images. What is the reason for using OCI guidelines?

- To standardize the image formats
- To ensure that images can execute on OCI compliant runtimes

| DOCKER COMMAND                                                                       | OUTPUT                                                  |
| ------------------------------------------------------------------------------------ | ------------------------------------------------------- |
| **Build a Docker image using `Dockerfile.staging file` in the `app/backend` folder** | `docker build \ -f Dockerfile.staging app/backend`      |
| **Create an interactive shell to a `busybox` container**                             | `docker run -it busybox`                                |
| **Tag the new image ID as the front-end application in `versionv4.5.2`**             | `docker tag f10f0a406345 \ pixelpotato/frontend:v4.5.2` |
| **Push the new front-end application to DockerHub**                                  | `docker push \ pixelpotato/frontend:v4.5.2`             |
| **Login into the DockerHub using valid credentials**                                 | `docker login`                                          |

---

## [Docker for Application Packaging Exercise](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/78ec0fc2-99c0-4abf-9310-85a2bb5dd42d)

- [Solution](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/ff34636a-df61-4ad4-9aa7-f9c73a25d485)

---

## How docker works?

1. It packages apps into a single unit called an image.
2. When you run these images via docker, they are called containers.
3. A single container is an instance of an image.
4. You can run many containers based out of single image.
5. A common analogy is to imagine containers like shipping containers. The content of the container may vary, but because they are similarly shaped (containers), they can be handled the same way.
6. However, often, containers are related, and they may be sent to a single location.
7. In docker, the contents of a container come together to form a singular unit that represents an app, service or any piece of software.
8. A dockerized app contains all the services, programs and libraries you need along with the instruction on how to run the dockerized app and the environment.
9. An image is an immutable that is a snapshot of a container.
10. Imagines are constructed with build command and executed with a container with the run command.
11. Images are stored in the docker registry and used when needed.
12. Large images are composed of layers of other images.
13. The advantage of layers is that it can be transferred easily.

---

## Hands-On Open Source CI/CD Tools:

1. Install a Oracle Virtual box/VM-Ware on your local system.
2. Deploy a Linux(ubuntu) VM.
3. Install the putty client for SSH connection.
4. Install all the dependencies.
5. Install the tool like git, Jenkins, Chef, etc. Which ever you wanted to learn.
6. Repeat the same.

---

## Resources

### GitHub

- [CompleteIntroToContainers](https://btholt.github.io/complete-intro-to-containers/), **GitHub**, _Bholt_

### 🎓 Courses

- [Docker For The Absolute Beginner](https://kodekloud.com/p/docker-for-the-absolute-beginner-hands-on), **Website**, _KodeKloud_
- [Docker for Beginners: Full Free Course](https://www.youtube.com/watch?v=zJ6WbK9zFpI), **YouTube**, _FreeCodeCamp_
- [DevOps Engineering Course for Beginners](https://www.youtube.com/watch?v=j5Zsa_eOXeY), **Website**, _FreeCodeCamp_
- [Learn Docker & Containers using Interactive Browser Based Labs](https://www.katacoda.com/courses/docker), **Website**, _Katacoda_
- [IBM Cloud Essentials Course](https://www.ibm.com/blogs/ibm-training/get-ready-for-ibm-cloud-certification-with-new-free-ibm-cloud-essentials-course/), **Website**, _IBM_
- [Learn Docker by Building a Node / Express App](https://www.freecodecamp.org/news/learn-docker-by-building-a-node-express-app/), **YouTube**, _FreeCodeCamp_
- [Docker in 1 Hour](https://www.youtube.com/watch?v=pTFZFxd4hOI), **YouTube**, _Programming with Mosh_
- [Docker Essentials](https://www.udemy.com/cart/subscribe/course/1948098/), **Udemy**, _Cerulean Canvas_

### 📝 Blog Post

- [Docker Tutorial Complete Beginner's Guide](https://purnasatria.medium.com/docker-tutorial-complete-beginners-guide-8b7dd2362c35?sk=c908d8e1b17838f6a6878a3147dc39fb), **Medium**, _Punasatria_
- [What is Docker Used For? A Docker Container Tutorial for Beginners](https://www.google.com/amp/s/www.freecodecamp.org/news/what-is-docker-used-for-a-docker-container-tutorial-for-beginners/amp/), **FreeCodeCamp**, _LucasSantos_
- [Differences between a Dockerfile, Docker Image and Docker Conatiner](https://nickjanetakis.com/blog/differences-between-a-dockerfile-docker-image-and-docker-container), **Website**, _Nick Janetakis_
- [Get to Know Docker's Ecosystem](https://nickjanetakis.com/blog/get-to-know-dockers-ecosystem), **Website**, _Nick Janetakis_
- [Best Practices for building containers](https://dev.to/ankit01oss/best-practices-for-building-containers-4mkp), **Dev To**, _NickKanetAkis_
- [Build your Python image](https://docs.docker.com/language/python/build-images/), **Website**, _Docker Docs_
- [Dockerize You Data Science Project, A Quick Guide](https://pub.towardsai.net/how-to-dockerize-your-data-science-project-a-quick-guide-b6fa2d6a8ba1), **Medium**, _TowardsAI_

### 🎥 Video Blogs

- [Exercise 1: Docker for Application Packaging](https://www.youtube.com/watch?v=zcENH_nvPCU&index=3), **YouTube**, _MLOps Ninja_
- [Docker in 100 Second](https://www.youtube.com/watch?v=Gjnup-PuquQ), _Fireship_, **YouTube**
- [How To Dockerize in 7 Easy Steps](https://www.youtube.com/watch?v=gAkwW2tuIqE) , **YouTube**, _Fireship_
- [Containerization Explained](https://www.youtube.com/watch?v=0qotVMX-J5s), **YouTube**, _IBM Cloud_
- [Introduction to Kubernetes and Docker](https://www.youtube.com/watch?v=PfRWP60qxPM), **YouTube**, _Caleb Curry_
- [Kubernetes vs Docker](https://www.youtube.com/watch?v=2vMEQ5zs1ko&t=389s), **YouTube**, _IBM Cloud_
- [Intro to Microservices, Dockerm and Kubernetes](https://www.youtube.com/watch?v=1xo-0gCVhTU), **YouTube**, _James Quigley_

### 🛠️ Tools

- [Labs Play with Docker](https://labs.play-with-docker.com/)

---

## Refactor Todo

- [Practical Docker for DevOp Beginners](https://www.udemy.com/course/docker-for-beginners-tutorial-with-practical-example/?LSNPUBID=6atJFJ4NNe4), **Udemy**
- [Web Dev Continuous integration w/ Jenkins](https://www.udemy.com/course/continuous-integration-with-jenkins/?LSNPUBID=6atJFJ4NNe4), **Udemy**
- [DevOps CI/CD w/ Jenkins Pipelines Groovy DSL](https://www.udemy.com/course/devops-crash-course-cicd-with-jenkins-pipelines-groovy-dsl/?LSNPUBID=6atJFJ4NNe4), **Udemy**
- [SUSE & Rancher Community](https://community.suse.com/share/F1pMnGSvpP0S8gMl?utm_source=manual), **SUSE & Rancer Community**

---

- [Create Docker Container with Flask Seaborn Regression Plot App](https://www.coursera.org/projects/create-docker-container-seaborn-regression-plot-app)
- [What is Docker? | AWS](https://aws.amazon.com/docker/)
- [Free Docker Tutorial - Docker Tutorial for Beginners practical hands on -Devops | Udemy](https://www.udemy.com/course/docker-for-beginners-tutorial-with-practical-example/?LSNPUBID=6atJFJ4NNe4)
- [Free Microsoft Azure DevOps Tutorial - AZ-400 Part 3 - Azure DevOps - CI and CD | Udemy](https://www.udemy.com/course/azure-devops-ci-and-cd/?LSNPUBID=6atJFJ4NNe4)
- [Learning Docker](https://www.linkedin.com/learning/learning-docker-2018)
- [Docker Cookbook - Second Edition Free eBook | Packt](https://www.packtpub.com/free-ebook/docker-cookbook-second-edition/9781788626866)
- [Docker Tutorial for Beginners [FULL COURSE in 3 Hours] - YouTube](https://www.youtube.com/watch?v=3c-iBn73dDE)
- [Containers vs VMs: What's the difference? - YouTube](https://www.youtube.com/watch?v=cjXI-yxqGTI)
- [(159) Docker For Beginners: From Docker Desktop to Deployment - YouTube](https://www.youtube.com/watch?v=i7ABlHngi1Q)
- [When To Use Microservices (And When Not To!) • Sam Newman & Martin Fowler • GOTO 2020 - YouTube](https://www.youtube.com/watch?v=GBTdnfD6s5Q)
- [Docker and Kubernetes Tutorial | Full Course [2021] - YouTube](https://www.youtube.com/watch?v=bhBSlnQcq2k)
- [Docker and Kubernetes Tutorial | Full Course [2021] - YouTube](https://www.youtube.com/watch?v=bhBSlnQcq2k)
- [Docker Tutorial for Beginners - A Full DevOps Course on How to Run Applications in Containers - YouTube](https://www.youtube.com/watch?v=fqMOX6JJhGo)
- [WSL 2 with Docker getting started - YouTube](https://www.youtube.com/watch?v=5RQbdMn04Oc)
- [What is Docker | Docker Tutorial for Beginners | Docker Container | DevOps Tools | Edureka - YouTube](https://www.youtube.com/watch?v=lcQfQRDAMpQ)
- [(3530) Docker, desde tu computadora hasta la nube de AWS - YouTube](https://www.youtube.com/watch?v=xtXRIM-q6qc)
- [(1382) Learn Docker in 7 Easy Steps - Full Beginner's Tutorial - YouTube](https://www.youtube.com/watch?v=gAkwW2tuIqE)
- [(164) Episode 75 - The Return of Docker/Dagger's Solomon Hykes - YouTube](https://www.youtube.com/watch?v=oMAGtvVfcRk)
- [What exactly is Docker?. An introduction to containers and… | by Burak Karakan | The Startup | Medium](https://medium.com/swlh/what-exactly-is-docker-1dd62e1fde38)
- [Docker — Beginner’s Guide — Part 1: Images & Containers | by Sebastian Eschweiler | CodingTheSmartWay.com Blog | Medium](https://medium.com/codingthesmartway-com-blog/docker-beginners-guide-part-1-images-containers-6f3507fffc98)
- [Welcome Docker!. After we write a code for an… | by Astha Upadhyay | Jun, 2021 | Medium](https://aucodes.medium.com/journey-from-source-to-image-f547097571ec)
- [Docker Container Security: Challenges and Best Practices | by WhiteSource | Medium](https://medium.com/@WhiteSourceSoft/docker-container-security-challenges-and-best-practices-70707b84eb36)
- [6 Kubernetes Security Best Practices Every Linux Administrator Should Know — LinuxTechLab | by LinuxTechLab | Medium](https://linuxtechlab.medium.com/6-kubernetes-security-best-practices-every-linux-administrator-should-know-linuxtechlab-2d1a4239d2f3)
- [Container Security Checklist | Medium](https://htayyar.medium.com/container-security-bes-practices-d4c2f5c01247)
- [Container Security: 5 Best Practices for Building with Docker | by ExitCertified (Tech Data) | ExitCertified (Tech Data) | Medium](https://medium.com/exitcertified-tech-data/container-security-5-best-practices-for-building-with-docker-864e31a12328)
- [Running GUI applications on docker container | by Harsh Goenka | Geek Culture | May, 2021 | Medium](https://medium.com/geekculture/running-gui-applications-on-docker-container-e552b9ff2945)
- [Installing Docker on Window 10\. Want to learn docker?…Want to execute… | by Tushar Soam | Medium](https://medium.com/@tushar0618/installing-docker-desktop-on-window-10-501e594fc5eb)
- [Reset your lost password using Docker and SSH | by Alex Ellis | Medium](https://alexellisuk.medium.com/reset-your-lost-password-using-docker-and-ssh-f09940c592e9)
- [Best Practices for building containers - DEV Community](https://dev.to/ankit01oss/best-practices-for-building-containers-4mkp)
- [Docker CMD vs ENTRYPOINT: explaining the difference - DEV Community](https://dev.to/hood/docker-cmd-vs-entrypoint-explaining-the-difference-55g7)
- [Use Kool to run Multiple Docker Applications at the same time in your Local Development Environment - DEV Community](https://dev.to/kooldev/use-kool-to-run-multiple-docker-applications-at-the-same-time-in-your-local-development-environment-5ec6)
- [Docker for Dummies - DEV Community](https://dev.to/stevenmcgown/docker-for-dummies-2bff)
- [Docker for Dummies - DEV Community](https://dev.to/stevenmcgown/docker-for-dummies-2bff)
- [The Foobar challenge: Google’s hidden test for developers](https://www.freecodecamp.org/news/the-foobar-challenge-googles-hidden-test-for-developers-ed8027c1184/)
- [The Docker Handbook – 2021 Edition](https://www.freecodecamp.org/news/the-docker-handbook/)
- [The Docker Handbook – 2021 Edition](https://www.freecodecamp.org/news/the-docker-handbook/)
- [hadolint/hadolint: Dockerfile linter, validate inline bash, written in Haskell](https://github.com/hadolint/hadolint)
- [hrittikhere (Hrittik Roy)](https://github.com/hrittikhere)
- [easychen/docker2saas: An open source tool that lets you create a SaaS website from docker images in 10 minutes.](https://github.com/easychen/docker2saas)
- [See Docker Bangalore Joint Meetup with JFrog & Collabnix Community at Docker Bangalore](https://events.docker.com/events/details/docker-bangalore-presents-docker-bangalore-joint-meetup-with-jfrog-collabnix-community/)
- [Build Docker Kubernetes-ready Applications on your Desktop | Docker](https://www.docker.com/products/kubernetes)
- [Tech Preview: Docker Dev Environments - Docker Blog](https://www.docker.com/blog/tech-preview-docker-dev-environments/?utm_campaign=IT+Pro&utm_content=1624466321&utm_medium=social&utm_source=Organic)
- [Demystifying the Open Container Initiative (OCI) Specifications - Docker Blog](https://www.docker.com/blog/demystifying-open-container-initiative-oci-specifications/)
- [Play with Docker | Docker](https://www.docker.com/play-with-docker)
- [Build Docker Kubernetes-ready Applications on your Desktop | Docker](https://www.docker.com/products/kubernetes)
- [Level Up Security with Scoped Access Tokens - Docker Blog](https://www.docker.com/blog/level-up-security-with-scoped-access-tokens/)
- [Improved Volume Management, Docker Dev Environments and more in Desktop 3.5 - Docker Blog](https://www.docker.com/blog/improved-volume-management-docker-dev-environments-and-more-in-desktop-3-5/)
- [Docker Commands Cheat Sheet {With Downloadable PDF} | PhoenixNAP](https://phoenixnap.com/kb/list-of-docker-commands-cheat-sheet)
- [Best practices for writing Dockerfiles | Docker Documentation](https://docs.docker.com/develop/develop-images/dockerfile_best-practices/)
- [DockerCon 2021 | How Much Kubernetes Do I Need to Learn?](https://docker.events.cube365.net/dockercon-live/2021/content/Videos/zo9AAafDLCPRv2rom?mkt_tok=NzkwLVNTQi0zNzUAAAF99VOgytfSLiAYBfkHu0ON8-uQmEgIcPW0AMCZfLHT_Hwhlv7b9djmoYp9k0kC4YC5R3jxFzXEcWfEkU8QPTk3JbopYoQ--Z8j5FXBVI0)
- [DockerCon 2021 | A Pragmatic Tour of Docker Filesystems](https://docker.events.cube365.net/dockercon-live/2021/content/Videos/TQhsXpfXpcDnvDFkj?mkt_tok=NzkwLVNTQi0zNzUAAAF99VOgyt2bMtJrafzVU_IgFUgPyFPY-0aAHorTXjytfCJfAITcL_u11jGAwyJTfGywg7ax8-0aqhR-N3FD36zohfrWjAu3CMTyBgoozL4)
- [DockerCon 2021 | Top Dockerfile Security Best Practices](https://docker.events.cube365.net/dockercon-live/2021/content/Videos/xRDsN4gNhEE6B7ufT?mkt_tok=NzkwLVNTQi0zNzUAAAF99VOgym2_GnE0035FCkgW36xi20lDAzirHlcsvOVZBxNxSFOCJSnV5jx1t_3iEHoq49zpc-dtaIbGiS_-PIS0vN6NVNGBjLA98OJtNPo)
- [Dockercon 2021 | DockerCon 2021](https://docker.events.cube365.net/dockercon-live/2021/)
- [What is Docker? | Opensource.com](https://opensource.com/resources/what-docker)
- [What is virtualization? | Opensource.com](https://opensource.com/resources/virtualization#:~:text=Virtualization%20is%20the%20process%20of,on%20a%20computer%20system%20simultaneously)
- [hadolint/hadolint: Dockerfile linter, validate inline bash, written in Haskell](https://github.com/hadolint/hadolint)
- [Start Playing - Quizizz](https://quizizz.com/join/pre-game/running/U2FsdGVkX1%252FKpbG%252FU6g3t8oUN9%252BQyGmJgPwSgjUTKiB9Qx%252B0iLqOvOIPmzXO1jJqMfXR7XRHDzqByyLwqQqFyQ%253D%253D/start)
- [How to Get Install Docker On Ubuntu 20.04 LTS - TREND OCEANS](https://trendoceans.com/how-to-get-install-docker-on-ubuntu-20-04-lts/#install-docker-from-ubuntu-repo)
- [Learn the history and fundamentals of Kubernetes - YouTube](https://www.youtube.com/watch?v=GKXpcuR55GI)
- [8 Steps for Migrating Existing Applications to Microservices](https://insights.sei.cmu.edu/blog/8-steps-for-migrating-existing-applications-to-microservices/)
- [Absolute Beginner’s Guide to Docker – Webinar Recording | The .NET Tools Blog](https://blog.jetbrains.com/dotnet/2021/06/25/absolute-beginner-s-guide-to-docker-webinar-recording/)
- [Top 20 Dockerfile best practices for security | Sysdig](https://sysdig.com/blog/dockerfile-best-practices/)
- [Getting started with Docker and Kubernetes: a beginners guide](https://www.educative.io/blog/docker-kubernetes-beginners-guide)
- [Lesson-3[Docker] Container Orchestration with Kubernetes](https://www.notion.so/Lesson-3-Docker-Container-Orchestration-with-Kubernetes-1cacea429a974f99911abd49bf8dfd2a)
- [List of 9 Best Docker Use Cases | Knowledgenile](https://www.knowledgenile.com/blogs/docker-use-cases/)
- [Docker Image VS Container: What is the difference?](https://phoenixnap.com/kb/docker-image-vs-container)
- [Dockercon 2021 | DockerCon 2021](https://docker.events.cube365.net/dockercon-live/2021?utm_source=docker&utm_medium=webreferral&utm_campaign=web-page-referral)
- [How to Dockerize a React + Flask Project - miguelgrinberg.com](https://blog.miguelgrinberg.com/post/how-to-dockerize-a-react-flask-project)
- [Docker Labs | Kode Kloud](https://www.kodekloud.com/p/docker-labs)
- [docs.docker.com](https://docs.docker.com/desktop/kubernetes/)
- [LXC vs Docker: What is the difference between Lxc and Docker? - Best DevOps](https://www.bestdevops.com/lxc-vs-docker-what-is-the-difference-between-lxc-and-docker/)
- [Vagrant Tutorials - HashiCorp Learn](https://learn.hashicorp.com/vagrant)
- [Docker - Full Stack Python](https://www.fullstackpython.com/docker.html)
- [Building Minimal Docker Containers for Python Applications | by Nick Joyce | Real Kinetic Blog](https://blog.realkinetic.com/building-minimal-docker-containers-for-python-applications-37d0272c52f3)
- [SysVinit to Systemd Cheatsheet - Fedora Project Wiki](https://fedoraproject.org/wiki/SysVinit_to_Systemd_Cheatsheet)
- [Free Docker Tutorial for Beginners](https://www.eduonix.com/courses/Software-Development/docker-for-beginners)
- [SUSE & Rancher Community](https://community.suse.com/feed?autojoin=1)
- [Cloud Run documentation  |  Cloud Run Documentation  |  Google Cloud](https://cloud.google.com/run/docs)
- [DevOps BootCamp — OSU DevOps BootCamp 0.0.1 documentation](https://devopsbootcamp.osuosl.org/index.html)
- [A Beginner’s Guide to Understanding and Building Docker Images](https://jfrog.com/knowledge-base/a-beginners-guide-to-understanding-and-building-docker-images/?utm_source=mkto&utm_medium=email&utm_campaign=Get-started-with-docker&utm_term=engagement&utm_content=2021)
- [[FREE Class] Docker & Kubernetes For Beginners Certification (CKA) & Demo](https://k21academy.com/free-masterclass-dockers-kubernetes-administrations-with-certifications/?utm_source=google&utm_medium=cpc&utm_campaign=cka_gmail_remarketing_rest_countries&gclid=Cj0KCQjw5auGBhDEARIsAFyNm9GGcHFeRNSTcUwz1bqN8Nw8627ebAawfDxPgJdsTbxENkCFEDZUjGcaAreBEALw_wcB)
- [SOA vs. Microservices: What’s the Difference? | IBM](https://www.ibm.com/cloud/blog/soa-vs-microservices)
- [What is CI/CD? Continuous integration and continuous delivery explained | InfoWorld](https://www.infoworld.com/article/3271126/what-is-cicd-continuous-integration-and-continuous-delivery-explained.html)
- [Introduction to Docker containers - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/intro-to-docker-containers/)
- [SUSE and Rancher Community - Apps on Google Play](https://play.google.com/store/apps/details?id=com.mightybell.suse)
- [Build a containerized web application with Docker - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/intro-to-containers/?WT.mc_id=udacity_learn-wwl)
- [Build and store container images with Azure Container Registry - Learn | Microsoft Docs](https://docs.microsoft.com/en-us/learn/modules/build-and-store-container-images/?WT.mc_id=udacity_learn-wwl)
- [Sign Up | CNCN Community](https://community.cncn.io/sign_up?from=https%3A%2F%2Fcommunity.cncn.io%2F%3Fautojoin%3D1&space_id=3144543)
- [Deploy code faster: with CI/CD and Kubernetes](https://cloud.google.com/kubernetes-engine/kubernetes-comic)
- [Docker Registry V2](https://www.slideshare.net/Docker/docker-registry-v2)
- [Aqua Security: 50% of new Docker instances attacked within 56 minutes | VentureBeat](https://venturebeat.com/2021/06/28/aqua-security-50-of-new-docker-instances-attacked-within-56-minutes/)
- [Virtual machines to containers: How to make a seamless transition](https://techgenix.com/virtual-machines-to-containers/)
- [Cloud Native Architecture Fundamentals Quiz](https://docs.google.com/forms/d/e/1FAIpQLSeDCfe_GdnX11hnUhAVr_AGZTAuyXGgVEWLDjm5GVSYufVsAw/closedform)
- [Docker ADD vs COPY: What is the Difference and Which One to Use?](https://phoenixnap.com/kb/docker-add-vs-copy)
- [fhsinchy/docker-handbook-projects: Project codes used in "The Docker Handbook"](https://github.com/fhsinchy/docker-handbook-projects)
- [How to Dockerize a React + Flask Project - miguelgrinberg.com](https://blog.miguelgrinberg.com/post/how-to-dockerize-a-react-flask-project)
- [Remote k8s with docker-desktop using an SSH tunnel](https://gist.github.com/alfredodeza/4c262b71fec683a61d7a54df9625a995)
- [Dockerfile Linter](https://hadolint.github.io/hadolint/)
- [Module 4: Migrate from Google App Engine to Cloud Run with Docker](https://codelabs.developers.google.com/codelabs/cloud-gae-python-migrate-4-rundocker?hl=en#0)
- [MongoDB with Docker: Get started in 5 minutes](https://www.educative.io/blog/mongodb-with-docker)
- [Advantages of Using Docker for Microservices in 2020](https://rubygarage.org/blog/advantages-of-using-docker-for-microservices)
- [Rancher Docs: Installing Rancher on a Single Node Using Docker](https://rancher.com/docs/rancher/v2.5/en/installation/other-installation-methods/single-node-docker/)
- [The Ultimate Docker Cheat Sheet | dockerlabs](https://dockerlabs.collabnix.com/docker/cheatsheet/)
- [Containers as a Service: A Complete Guide for Beginners | CloudThat's Blog](https://blog.cloudthat.com/containers-as-a-service-a-complete-guide-for-beginners/)
- [Container Solutions](https://jobs.lever.co/container-solutions?lever-via=b-scCr8W_a)
- [Container storage for dummies](https://www.redhat.com/en/resources/container-storage-dummies)
- [introduction-to-containers · main · iduoad / Agora / Talks · GitLab](https://gitlab.com/idspace/agora/talks/-/tree/main/introduction-to-containers)
- [Docker for the Absolute Beginner - Hands On - DevOps | Udemy](https://www.udemy.com/course/learn-docker/)
- [Attach and Detach From a Docker Container | Baeldung](https://www.baeldung.com/ops/docker-attach-detach-container)
- [Demystifying Containers – Part IV: Container Security | SUSE Communities](https://www.suse.com/c/demystifying-containers-part-iv-container-security/)
- [Top 20 Dockerfile best practices for security | Sysdig](https://sysdig.com/blog/dockerfile-best-practices/)
- [FOSDEM 2021 - Docker Is No More! What Now?](https://fosdem.org/2021/schedule/event/containers_k8s_docker/)
- [How to Quickly Deploy WordPress as a Docker Container](https://www.cloudsavvyit.com/12978/how-to-quickly-deploy-wordpress-as-a-docker-container/amp/)

---

## Related

[[README]]
[[docker_commands]]
[[vm-to-containers]]
