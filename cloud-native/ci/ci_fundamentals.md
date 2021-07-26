# CI Fundamentals

Summary
Continuous Integration (CI) is a mechanism that produces the package of an application that can be deployed to consumers. As such, every commit to the main branch is built, tested, and packaged, if it meets the expected behavior. Within the cloud-native, the result of Continuous Integration represents a Docker image or an artifact that is OCI compliant.

Let's explore the commands and tools associated with each Continuous Integration stage!

Diagram of stages included in the Continuous Integration
Continuous Integration stages

Build
The build stage compiles the application source code and associated dependencies. We have explored this stage as part of the Dockerfile. For example, the Dockerfile for the Python hello-world application instructed the installation of dependencies from requirements.txt file and execution of the app.py at the container start.

# use pip to install any application dependencies

RUN pip install -r requirements.txt

# execute command on the container start

CMD [ "python", "app.py" ]
Test
The technology landscape provides an abundance of frameworks, libraries, and tools to test and validate the behavior of an application. For Python application, some of the well-known frameworks are:

pytest - for functional testing of the application
pylint - for static code analysts of the application codebase
Package
The result of the package stage is an executable that contains the latest features and their dependencies. With Docker, this stage is implemented using docker build and docker push commands. These create a Docker image using a Dockerfile, and stores the image to a registry, such as DockerHub. For example, to create and store the image for Python hello-world application, the following commands are used:

# build an image using a Dockerfile

docker build -t python-helloworld .

# store and distribute an image using DockerHub

docker push pixelpotato/python-helloworld:v1.0.0
Note: Buildbacks does not require a Dockerfile to create an OCI compliant image or artifact.

Github Actions

Summary
There are plenty of tools that automate the Continuous Integration stages, such as Jenkins, CircleCI, Concourse, and Spinnaker. However, in this lesson, we will explore GitHub Actions to build, test, and package an application.

GitHub Actions are event-driven workflows that can be executed when a new commit is available, on external or scheduled events. These can be easily integrated within any repository and provide immediate feedback if a new commit passes the quality check. Additionally, GitHub Actions are supported for multiple programming languages and can offer tailored notifications (e.g. in Slack) and status badges for a project.

A GitHub Action consists of one or more jobs. A job contains a sequence of steps that execute standalone commands, known as actions. When an event occurs, the GitHub Action is triggered and executes the sequence of commands to perform an operation, such as code build or test.

Diagram of the GitHub Actions structure
GitHub Actions structure

Let's configure a GitHub Action that prints the Python version!

GitHub Actions are configured using YAML syntax, hence uses the .yaml or .yml file extensions. These files are stored in .github/workflows directory within the code repository. Within this folder, the python-version.yml contains the following sections:

## file location and name: # .github/workflows/python-version.yml

## Named of the workflow.

name: Python version

## Set the trigger policy.

## In this case, the workflow is execute on a `push` event,

## or when a new commit is pushed to the repository

on: [push]

## List the steps to be executed by the workflow

jobs:

## Set the name of the job

check-python-version: ## Configure the operating system the workflow should run on. ## In this case, the job on Ubuntu
runs-on: ubuntu-latest ## Define a sequence of steps to be executed
steps: ## Use the public `checkout` action in version v2

## to checkout the existing code in the repository - uses: actions/checkout@v2 ## Use the public `setup-python` action in version v2

## to install python on the Ubuntu based environment - uses: actions/setup-python@v2 ## Executes the `python --version` command - run: python --version

On the successful execution of the workflow, the Python version is printed. For example, Python 3.9.0.

Github Actions Walkthrough
Note: To follow this demo make sure you fork the course repository and reference the python-helloworld application.

This demo provides a step-by-step guide of how to write a GitHub Action to run a suite of pytests.

Pytest is a framework that is used to write functional testing for an application. In this example, within the test_with_pytest.py we create a mock test that will always execute successfully.

Summary

## Define a test that will always pass successfully

def test_always_passes():
assert True
Once we have completed writing the test, we can construct a GitHub Action that will execute the tests using pytest tool. For this purpose, a new workflow is defined in the pytest.yml file within the .github/workflows directory.

To trigger the workflow a new commit is necessary (e.g. editing the README.md fie). On the successful execution of the GitHub Action, we should see an output mentioning that all the test passed successfully (as expected):

Run pytest
============================= test session starts ==============================
platform linux -- Python 3.8.6, pytest-6.2.1, py-1.10.0, pluggy-0.13.1
rootdir: /home/runner/work/nd064_course_1/nd064_course_1
collected 1 item

solutions/python-helloworld/test_with_pytest.py . [100%]

============================== 1 passed in 0.02s ===============================
Also, this demo showcases the "Python version" GitHub Action that was used as an example in the slides.

Further reading
Explore GitHub Actions in more detail:

Introduction to GitHub Actions
Create an example workflow
Inspect public workflows on GitHub Marketplace

---

Quizzes: The CI Fundamentals
QUESTION 1 OF 3
You are provided with a Python front-end application. Match each Continuous Integration stage with the commands used to implement the expected operations.

Submit to check your answer choices!
STAGES

COMMANDS

Run tests using Python testing frameworks

Install application dependencies

Build the image of the application

Store the Docker image in a registry

QUESTION 2 OF 3
What are the characteristics of a typical Continuous Integration implementation?

Triggered at each commit

The output can be an OCI compliant image

QUESTION 3 OF 3
What is the most suitable characteristic for GitHub Actions?

Event-driven workflows

---

Exercise: Continuous Application Deployment
Continuous Integration (CI) implies the integration of code into a shared repository, where at each push to the main branch, the code is built and tested. Frequently, the result of CI represents an artifact or a Docker image.

In this exercise, you will use GitHub Actions to automate the packaging of an application. This is a quite challenging exercise because you are provided with all the necessary documents and you will explore some of the actions on your own.

Being able to explore documents and tackle tasks independently is important. Take this opportunity and have fun! However, if you do need some help, feel free to check out the video on the solution page.

Environment Setup
Prepare the GitHub repository and application to test GitHub actions:

Task List

Exercise
Create a new GitHub Actions in the /.github/workflows/docker-build.yml that will build and push the Docker image for a Python web application, with the following requirements:

Image name: python-helloworld
Tag: latest
Platforms: platforms: linux/amd64,linux/arm64
GitHub marketplace has a rich suite of upstream actions that can be easily integrated within a repository. One of the upstream action is Build and Push Docker images, which can be used to implement the required CI task.

The above GitHub action uses DockerHub Tokens and encrypted GitHub secrets to login into DockerHub and to push new images. To set up these credentials refer to the following resources:

Create DockerHub Tokens
Create GitHub encrypted secrets
Note: you will need a Dockerfile to build the image.

---

Solution: The CI Fundamentals

GitHub has a rich library of upstream actions that can be easily integrated with any repository. The suite includes a Build and push Docker images action which uses 3 main components:

login - to logging into DockerHub
setup-buildx - to use an extended Docker CLI build capabilities
setup-qemu - to enable the execution of different multi-architecture containers
The following snippet showcases the Docker build and push of the application, under .github/workflows/docker-build.yaml file:

# This is a basic workflow to help you get started with Actions

name: Docker Build and Push

# Controls when the action will run. Triggers the workflow on push or pull request

# events but only for the master branch

on:
push:
branches: [ master ]
pull_request:
branches: [ master ]

# A workflow run is made up of one or more jobs that can run sequentially or in parallel

jobs:

# This workflow contains a single job called "build"

build: # The type of runner that the job will run on
runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      -
        name: Checkout
        uses: actions/checkout@v2
      -
        name: Set up QEMU
        uses: docker/setup-qemu-action@v1
      -
        name: Set up Docker Buildx
        uses: docker/setup-buildx-action@v1
      -
        name: Login to DockerHub
        uses: docker/login-action@v1
        with:
          username: ${{ secrets.DOCKERHUB_USERNAME }}
          password: ${{ secrets.DOCKERHUB_TOKEN }}
      -
        name: Build and push
        uses: docker/build-push-action@v2
        with:
          context: .
          file: ./Dockerfile
          platforms: linux/amd64
          push: true
          tags: {{ YOUR_DOCKERHUB_REPOSITORY }}/python-helloworld:latest

The Docker build and push workflow can be found in course repository. Make sure to move this file to .github/workflows/docker-build.yaml location to execute it.

---

## Related Foam Link
