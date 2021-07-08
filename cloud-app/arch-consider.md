# Arch Consider

[Course](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/fcc8c401-8331-4214-9609-f2f8529f50a1/concepts/cf916761-c237-4646-b398-bc5f9bd2fc35)

---

## Design Considerations for Cloud

### Requirements

The first thing is what are you building and who is going to use it. Suppose if you are making an app for communication then you will have to define who is going to use it, is it going to be used internally by the employees of your company or are you making a product for your customer so that chat with their friends and family, is it going to be a messaging application or video calling app or maybe both, will it have a mobile app for both android and iOS or will it be a web based app, and then you can decide which technologies you are going to use to build your app These are the questions you will need to answer before you start coding your new application.

### Resources

Now that you have answered all the big and hard questions it's time to look around and gather all the resources you have and utilize them effectively. Follow these points for better usage of your resources.

- How much time do you have.?
- Do you have a financial budget.?
- Are there employees who can build a mobile application for both android and iOS.?
- Do you need to train them first.?
- Can you outsource the project.?
- Do you know anything about the project.?
- Do you know someone who has worked on this type of project before.?

There can me more things than those listed above always think twice and do your research before using any resource.

---

## Monoliths and Micro-services

### Application tiers

Each product or software in our case has three main components namely **Frontend, Backend, and a Database.** the frontend handles what the end-user sees and how he interacts with our product the backend handles how the database interacts with the frontend and the database saves all our your end-users data and retrieves it when needed.

#### Monoliths

In a monolithic application you can only use one primary programming language and all three tiers of your application will be in the same unit, repository and will share all the resources and will have a single binary file.
In your chat application (monolithic version) the frontend, backend, and all the chats stored in the database will be in a single package.

#### Microservice

In a application that uses microservices you can use more than one programming language that you want to use the frontend can be divided into small parts the backend can be divided into modules and they all communicate with each other and the database and use only the allocated resources and have separated binaries.

---

## Trade-offs between Monoliths and Micro-services

---

## Best Practices for Application Development

- **DEBUG** - record fine-grained events of application processes
- **INFO** - provide coarse-grained information about an operation
- **WARN** - records a potential issue with the service
- **ERROR** - notifies an error has been encountered, however, the application is still running
- **FATAL** - represents a critical situation, when the application is not operational

### Further reading

- [Health Checks](https://microservices.io/patterns/observability/health-check-api.html) - explore the core reasons to introduce health checks and implementations examples
- [Prometheus Best Practices on Metrics Naming](https://prometheus.io/docs/instrumenting/writing_exporters/#metrics) - explore how to name, label, and define the type of metrics
- [Application Logging Best Practices](https://logz.io/blog/logging-best-practices/) - read more on how to define what logs should be collected by an application
- [Logging Levels](https://www.tutorialspoint.com/log4j/log4j_logging_levels.htm) - explore possible logging levels and when they should be enabled
- [Enabling Distributed Tracing for Micro-services With Jaeger in Kubernetes](https://containerjournal.com/topics/container-ecosystems/enabling-distributed-tracing-for-microservices-with-jaeger-in-kubernetes/) - learn what tools can be used to implement tracing in a Kubernetes cluster

### More Resources

- [The Importance of Application Health Checks and Monitoring](https://victorops.com/blog/regular-application-health-checks-and-monitoring)

---

## Edge Case: Amorphous Application

- **A split operation** - is applied if a service covers too many functionalities and it's complex to manage. Having smaller, manageable units is preferred in this context.
- **A merge operation** - is applied if units are too granular or perform closely interlinked operations, and it provides a development advantage to merge these together. For example, merging 2 separate services for log output and log format in a single service.
- **A replace operation** - is adopted when a more efficient implementation is identified for a service. For example, rewriting a Java service in Go, to optimize the overall execution time.
- **A stale operation** - is performed for services that are no longer providing any business value, and should be archived or deprecated. For example, services that were used to perform a one-off migration process.

- [Modern Banking in 1500 Micro-services](https://www.youtube.com/watch?v=t7iVCIYQbgk), watch how Monzo is managing thousands of micro-services and evolves their ecosystem.

---

## Related

- [[_cloud-app]]
