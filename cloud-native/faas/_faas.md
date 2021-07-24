# FaaS

## Summary

An organization will always explore the most efficient offering to deploy a product to consumers. PaaS solutions are lightweight on initial setup, as a team can release the code in production within days.

However, there are use cases where customers interact with a service only once a day or for a couple of hours within a day. For example, a service to update a timetable with the new bus schedule once a day. In this case, using a PaaS offering has one major downside: it is not cost-efficient. For example, with Cloud Foundry there will always be an instance of the application up and running, even if the service is used once a day. However, the team is billed for a full day.

For this scenario, a **FaaS** or **Function as a Service** is a more suitable offering. FaaS is an event-driven cloud-computing service that allows the execution of code without any management of the infrastructure and configuration files. As a result, the timetable update service is invoked only once a day, and for the rest of the time, there are no replicas of this service. A team will be billed only for the time the service is executed.

Popular FaaS solutions are AWS Lambda, Azure Functions, Cloud Functions from GCP, and many more.

Throughout the release process, a FaaS solution only requires the application code that is built and executed immediately. In comparison with a PaaS offering, this FaaS has a quicker usability rate, as no data management or configuration files are necessary.

Diagram of FaaS offering dependencies to deploy an application
FaaS dependencies to deploy an application

### New Terms

- **FaaS** or **Function as a Service** - event-driven cloud-computing service that requires only the application code to execute successfully.

## Further Reading

Explore FaaS in more detail:

- What is Function-as-a-Service (FaaS)?

## Function as a Service

- [Serverless (FaaS) vs. Containers - when to pick which?](https://www.serverless.com/blog/serverless-faas-vs-containers), **Serverless**
- [Serverless Vs Container (Lambda Vs Kubernetes)](https://www.youtube.com/watch?v=EpW28dvm_qo"), **YouTube**
- [Running serverless workload on Kubernetes](https://www.eventbrite.com/e/running-serverless-workload-on-kubernetes-with-knative-tickets-162340475733), **Eventbrite**, _Kubernetes Knative_
- [100 Seconds of ServerLess](https://youtu.be/W_VV2Fx32_Y), **YouTube**, _Fireship_

---

### Related
