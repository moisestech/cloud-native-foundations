# Mechanisms

## PaaS Mechanisms

PaaS Mechanisms

Summary
The industry is abundant with cloud-computing offerings that offer variate level of attraction of services. Some of the widely used cloud-computing services are:

On-premise - where an engineering team has full control over the platform, including the physical servers
IaaS or Infrastructure as a Service - where a team consumes compute, network, and storage resources from a vendor
PaaS or Platform as a Service - where the infrastructure is fully managed by a provider, and the team is focused on application deployment
Diagram of widely used cloud-computing service
Widely used cloud-computing offerings

Releasing a product to a production environment implies that a platform has been build to host this particular product. A platform consists of multiple services that need to be configured, wired, and maintained together. These services are:

Networking - establish communication between internal and external systems, such as internet connection, firewalls, routers, and cables
Storage- collect and store digital data, such as files, blocks, or objects
Servers - physical machines that provide compute services for a platform
Virtualization - abstracts physical servers, storage, and networking. For example, we have learned that hypervisors are used to virtualize servers.
O/S - operating systems that connect the software to physical resources (e.g. Linux, Ubuntu, Windows, etc)
Middleware - help the developers to build an application by making it easy to consume platform capabilities (e.g. messaging, API, data management)
Runtime - execution context for an application. For example, using JVM (or Java Virtual Machine) as a Java runtime
Data - tools for collection and storage of data that is required by an application during execution(e.g. MySQL, MongoDB, or CockroachDB)
Applications - the business logic for a product
On-premise
On-premise represents a cloud-computing offering where the engineering team has full control of the platform services (from networking to applications). This solution is suitable for organizations that have sufficient engineering power and regulations that demand full control of their technology stack and operations within it.

IaaS
IaaS solutions provide the abstraction of networking, storage, server, and virtualization layers. As a result, these services are consumed on-demand by the engineering teams. Additionally, IaaS provides a suitable abstraction for the management of self-hosted Kubernetes clusters, which depend on compute, network, and storage components for a successful bootstrap process.

The most common IaaS solutions are delivered by public cloud providers such as AWS, GCP, Microsoft Azure, and many more.

PaaS
PaaS is a cloud-computing offering that enables an engineering team to fully focus on application development. It abstracts all services except the application and the data associated with it. As a result, the team is required to manage the code base and any database service that the product needs to be fully operational.

Popular PaaS solutions are App Engine from GCP, Heroku, Cloud Foundry, Beanstalk from AWS, and many more.

Advantages:

Time-efficiency - engineering focus is shifter toward development rather than infrastructure management
Scalability and high availability - on-demand resource consumption enables an application to easily scale and fail-over
Rich application catalog - integration of external service (e.g. databases) with minimal effort
Disadvantages:

Vendor lock-in - it is challenging to interchange PaaS providers without service disruption
Data security - since data is managed by a 3rd party, an extra layer of complexity is added to ensure data confidentiality
Operational limitations - the service catalog is limited to the services offered by the integrated cloud provider
Diagram of different service that a cloud-computing service is capable of managing
Variate levels of service management from cloud-computing offerings

Throughout its evolution, an organization might use one or a subset of available cloud-computing services. It is essential to select an offering that closely meets business requirements. However, it is important to consider the following traits of cloud-computing services:

The fewer components are delegated to external providers, the more control there is over available functionalities
The more ownership there is across the stack, the more complexity is introduced in managing and delivering the product
The fewer components are managed by an engineering team, the quicker is the usability of the stack. As such, with a PaaS offering the engineering team can deploy their application immediately. While if choosing an on-premise solution, the release of a product is possible only after the platform is built.
Diagram showcasing the level of complexity vs usability of each cloud-computing service
Complexity vs Usability for each cloud-computing offering

New terms
On-premise - cloud-computing service, where a team owns the entire technology stack.
IaaS - cloud-computing service that offers the abstraction of networking, storage, server, and virtualization layers.
PaaS - cloud-computing service, where the infrastructure components are managed fully by a 3rd party provider, and a team manages only the application and the data associated with it.
Further Reading
Read more about on-premise, IaaS, and PaaS solutions:

On Premise Vs Cloud
Infrastructure as a Service
Platform as a Service
Cloud Computing in 2021: What You Should Know about Public, Private, Hybrid, PaaS, SaaS and FaaS

---

## Quizzes: PaaS Mechanisms

Quizzes: PaaS Mechanisms
QUESTION 1 OF 6
What services do you have to manage if you are using an on-premises solution?

Servers

Networking

Application

Middleware

QUESTION 2 OF 6
What services do you have to manage if you are using an IaaS solution?

Middleware

Data

Applications

QUESTION 3 OF 6
What services do you have to manage if you are using a PaaS solution?

Application

Data

QUESTION 4 OF 6
Which of the following cloud-computing offerings provides the most control of the infrastructure services?

On-premises

QUESTION 5 OF 6
Which of the following cloud-computing offerings provides quicker usability of infrastructure services?

PaaS

QUESTION 6 OF 6
Which of the following cloud-computing offerings provides a suitable abstraction level for a team to build and run their own Kubernetes clusters?

IaaS

---

## Exercise: PaaS Mechanisms

Exercise: PaaS Mechanisms
PaaS Consideration for a web-store
Platform as a Service (PaaS) provides a hosted environment for the efficient development and deployment of a project. Using this service truly allows developers to focus on building functionality instead of managing infrastructure components.

Imagine the following scenario: you are part of the small team that needs to refactor a web-store application. Currently, the application provides an inventory of thousands of products and is actively used by millions of customers daily. As a business, you want to guarantee service availability with minimal disruption during the refactoring/migration process. The application is managed in-house and is composed of front-end and backend microservices and a collection of databases to store the inventory and customer details.

The main reason for the refactoring process is the inability to cope with the high load of requests and poor end-user experience while using the web-store. Due to limited engineering resources, the aim is to introduce a new database solution and outsource the management to a 3rd party vendor. As well, the team desires to increase the visibility of the application by evaluating the monitoring and logging capabilities.

At this stage, you and your team decided that PaaS provides the most suitable solution. Using the above details, describe what PaaS functionalities will be highly beneficial for this project and elaborate on your reasoning.

PaaS Considerations
Describe what PaaS functionalities will be explicitly beneficial for this project and why

Your reflection
By default, the PaaS solutions offer the management of the underlying infrastructure, such as storage, databases, compute, hosting, and many more. Also, the majority of solutions will provide data analytics, security, and advanced scheduling.

As such, the web-store project will benefit from the following PaaS capabilities:

database - for storing the customer details, orders, and products details
compute - accessible scalability for the application to serve millions of customers
networking - hosting and serving the requests with no downtime
analytics - an add-on to collect data and provide metrics and logs about customer interaction with the web store.
Things to think about
One of the main advantages of choosing PaaS is the easy integration with available services from a provider.

Go to the solutions page to see the full explanation.

---

## Solution: PaaS Mechanisms

Solution: PaaS Mechanisms

By default, the PaaS solutions offer the management of the underlying infrastructure, such as storage, databases, compute, hosting, and many more. Also, the majority of solutions will provide data analytics, security, and advanced scheduling.

As such, the web-store project will benefit from the following PaaS capabilities:

database - for storing the customer details, orders, and products details
compute - accessible scalability for the application to serve millions of customers
networking - hosting and serving the requests with no downtime
analytics - an add-on to collect data and provide metrics and logs about customer interaction with the web-store
