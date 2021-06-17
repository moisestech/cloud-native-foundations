# Docker

- A tool that can package software into container that work reliably on any environment.
- Instead of virtualizing the hardware, containers only virtualize the OS (Operating System)
- All apps and containers are ran by a single kernel

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

## Transitions from VMs to Containers

---

## [Docker for Application Packaging Exercise](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/78ec0fc2-99c0-4abf-9310-85a2bb5dd42d)

- [Solution](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/ff34636a-df61-4ad4-9aa7-f9c73a25d485)

---

## Useful Docker Commands

---

## Resources

### Blog Post

- [Best Practices for building containers](https://dev.to/ankit01oss/best-practices-for-building-containers-4mkp)

### Video Blog

- [Docker in 100 Second](https://www.youtube.com/watch?v=Gjnup-PuquQ), _Fireship_
- [How To Dockerize in 7 Easy Steps](https://www.youtube.com/watch?v=gAkwW2tuIqE) _Fireship_

### Courses

- [Docker For The Absolute Beginner](https://kodekloud.com/p/docker-for-the-absolute-beginner-hands-on), _KodeKloud_

---

## Related

[[docker_commands]]
[[vm-to-containers]]
