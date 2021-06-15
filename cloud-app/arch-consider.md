# Arch Consider

[Course](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/fcc8c401-8331-4214-9609-f2f8529f50a1/concepts/cf916761-c237-4646-b398-bc5f9bd2fc35)

---

## Design Considerations for Cloud

---

## Monoliths and Micro-services

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

---

## Edge Case: Amorphous Application

- **A split operation** - is applied if a service covers too many functionalities and it's complex to manage. Having smaller, manageable units is preferred in this context.
- **A merge operation** - is applied if units are too granular or perform closely interlinked operations, and it provides a development advantage to merge these together. For example, merging 2 separate services for log output and log format in a single service.
- **A replace operation** - is adopted when a more efficient implementation is identified for a service. For example, rewriting a Java service in Go, to optimize the overall execution time.
- **A stale operation** - is performed for services that are no longer providing any business value, and should be archived or deprecated. For example, services that were used to perform a one-off migration process.

- [Modern Banking in 1500 Micro-services](https://www.youtube.com/watch?v=t7iVCIYQbgk), watch how Monzo is managing thousands of micro-services and evolves their ecosystem.
