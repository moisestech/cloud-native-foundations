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

## Resources

### GitHub

- [CompleteIntroToContainers](https://btholt.github.io/complete-intro-to-containers/), _Bholt_, GitHub

### Courses

- [Docker For The Absolute Beginner](https://kodekloud.com/p/docker-for-the-absolute-beginner-hands-on), _KodeKloud_, Website
- [Docker for Beginners: Full Free Course](https://www.youtube.com/watch?v=zJ6WbK9zFpI), _FreeCodeCamp_, YouTube
- [DevOps Engineering Course for Beginners](https://www.youtube.com/watch?v=j5Zsa_eOXeY), _FreeCodeCamp_, Website
- [Learn Docker & Containers using Interactive Browser Based Labs](https://www.katacoda.com/courses/docker), _Katacoda_, Website
- [IBM Cloud Essentials Course](https://www.ibm.com/blogs/ibm-training/get-ready-for-ibm-cloud-certification-with-new-free-ibm-cloud-essentials-course/), _IBM_, Website
- [Learn Docker by Building a Node / Express App](https://www.freecodecamp.org/news/learn-docker-by-building-a-node-express-app/), _FreeCodeCamp_, YouTube
- [Docker in 1 Hour](https://www.youtube.com/watch?v=pTFZFxd4hOI), _Programming with Mosh_, YouTube
- [Docker Essentials](https://www.udemy.com/cart/subscribe/course/1948098/), _Cerulean Canvas_, Udemy

### Blog Post

- [Best Practices for building containers](https://dev.to/ankit01oss/best-practices-for-building-containers-4mkp)
- [Build your Python image](https://docs.docker.com/language/python/build-images/), _Docker Docs_
- [Dockerize You Data Science Project, A Quick Guide](https://pub.towardsai.net/how-to-dockerize-your-data-science-project-a-quick-guide-b6fa2d6a8ba1), _TowardsAI_, Medium
- [Differences between a Dockerfile, Docker Image and Docker Conatiner](https://nickjanetakis.com/blog/differences-between-a-dockerfile-docker-image-and-docker-container), _Nick Janetakis_, Website
- [Get to Know Docker's Ecosystem](https://nickjanetakis.com/blog/get-to-know-dockers-ecosystem), _Nick Janetakis_, Website

### Video Blog

- [Exercise 1: Docker for Application Packaging](https://www.youtube.com/watch?v=zcENH_nvPCU&index=3), _MLOps Ninja_, YouTube
- [Docker in 100 Second](https://www.youtube.com/watch?v=Gjnup-PuquQ), _Fireship_, YouTube
- [How To Dockerize in 7 Easy Steps](https://www.youtube.com/watch?v=gAkwW2tuIqE) _Fireship_, YouTube
- [Containerization Explained](https://www.youtube.com/watch?v=0qotVMX-J5s), _IBM Cloud_, YouTube
- [Introduction to Kubernetes and Docker](https://www.youtube.com/watch?v=PfRWP60qxPM), _Caleb Curry_, YouTube
- [Kubernetes vs Docker](https://www.youtube.com/watch?v=2vMEQ5zs1ko&t=389s), _IBM Cloud_, YouTube
- [Intro to Microservices, Dockerm and Kubernetes](https://www.youtube.com/watch?v=1xo-0gCVhTU), _James Quigley_, YouTube

### Tools

- [Labs Play with Docker](https://labs.play-with-docker.com/)

---

## Refactor Todo

- [Free Docker Tutorial - Docker Tutorial for Beginners practical hands on -Devops](https://www.udemy.com/course/docker-for-beginners-tutorial-with-practical-example/?LSNPUBID=6atJFJ4NNe4)
- [Free Web Development Tutorial - Continuous integration with Jenkins](https://www.udemy.com/course/continuous-integration-with-jenkins/?LSNPUBID=6atJFJ4NNe4)
- [Free Jenkins Tutorial - DevOps Crash Course: CI/CD with Jenkins Pipelines Groovy DSL](https://www.udemy.com/course/devops-crash-course-cicd-with-jenkins-pipelines-groovy-dsl/?LSNPUBID=6atJFJ4NNe4)
- [SUSE & Rancher Community](https://community.suse.com/share/F1pMnGSvpP0S8gMl?utm_source=manual)

---

## Related

[[docker_commands]]
[[vm-to-containers]]
