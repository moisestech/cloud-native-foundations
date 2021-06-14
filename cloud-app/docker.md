# Docker

- A tool that can package software into container that work reliably on any environment.
- Instead of virtualizing the hardware, containers only virtualize the OS (Operating System)
- All apps and containers are ran by a single kernel

## 3 Elements of a Docker

1. **Docker File**
   - It's like DNA, it is code that tells Docker how to build an image.
2. **Image**
   - A snapshot of your software with all of its dependencies down to its operating system level.
   - The image is immutable which can be used to spin up multiple containers which is the actual software running in the real world.
3. **Container**
   - Actual Software running in the real world.

## Docker for Application Packaging

| Docker Component     | Purpose                                                  |
| -------------------- | -------------------------------------------------------- |
| **Docker File**      | Set of instructions to create a Docker Image             |
| **Docker Image**     | A read-only template that is used to spin-up a container |
| **Docker Container** | A runnable instance of the Docker image                  |
| **Docker Registry**  | A tool used to store and distribute Docker images        |

---

## Video Blog

- [Docker in 100 Second](https://www.youtube.com/watch?v=Gjnup-PuquQ), Fireship
- [Hoe To Dockerize in 7 Easy Steps](https://www.youtube.com/watch?v=gAkwW2tuIqE)
