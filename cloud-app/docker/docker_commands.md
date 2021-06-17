# Docker Commands

[Lesson 3: Useful Docker Commands](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/67dee0a1-d822-49d1-beef-fcdc77c6722f)

Docker provides a rich set of actions that can be used to build, run, tag, and push images. Below is a list of handy Docker commands used in practice.

**Note:** In the following commands the following arguments are used:

**OPTIONS** - define extra configuration through flags
**IMAGE** - sets the name of the image
**NAME**- set the name of the image
**COMMAND** and **ARG** - instruct the container to run specific commands associated with a set of arguments

---

## Build Images

To build an image, use the following command, where PATH sets the location of the Dockerfile and referenced application files:

<pre><code>docker build [OPTIONS] PATH</code></pre>

## Run Images

To run an image, use the following command:

<pre><code class="lang-bash">docker run [OPTIONS] IMAGE [COMMAND] [ARG...]</code></pre>

## Get Logs

To get the logs from a Docker container, use the following command:

<pre><code class="lang-bash">docker logs CONTAINER_ID</code></pre>

Where the CONTAINER_ID is the ID of the Docker container that runs an application.

## List images

To list all available images, use the following command:

<pre><code>docker images</code></pre>

## List containers

To list all running containers, use the following command:

<pre><code>docker ps</code></pre>

## Tag images

To tag an image, use the following command, where SOURCE_IMAGE defines the name of an image on the current machine and TARGET_IMAGE defines the repository, name, and version of an image:

<pre><code>docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]</code></pre>

## Login to DockerHub

To login into DockerHub, use the following command:

<pre><code>docker login</code></pre>

## Push Images

To push an image to DockerHub, use the following command:

<pre><code>docker push NAME[:TAG]</code></pre>

## Pull Images

To pull an image from DockerHub, use the following command:

<pre><code>docker pull NAME[:TAG]</code></pre>
