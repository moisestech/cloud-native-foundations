# Trade Offs

## Monoliths and Microservices

### Summary

- Prior to an organization delivers a product, the engineering team needs to decide on the most suitable application architecture. In most of the cases 2 distinct models are referenced: monoliths and microservices. Regardless of the adopted structure, the main goal is to design an application that delivers value to customers and can be easily adjusted to accommodate new functionalities.

- Also, each architecture encapsulates the 3 main tires of an application:
  - **UI (User Interface)** - handles HTTP requests from the users and returns a response
  - **Business logic** - contained the code that provides a service to the users
  - **Data layer** - implements access and storage of data objects

### Monoliths

In a monolithic architecture, application tiers can be described as:•part of the same unit•managed in a single repository•sharing existing resources (e.g. CPU and memory)•developed in one programming language•released using a single binaryImagine a team develops a booking application using a monolithic approach. In this case, the UI is the website that the user interacts with. The business logic contains the code that provides the booking functionalities, such as search, booking, payment, and so on. These are written using one programming language (e.g. Java or Go) and stored in a single repository. The data layer contains functions that store and retrieve customer data. All of these components are managed as a unit, and the release is done using a single binary.
MicroservicesIn a microservice architecture, application tiers are managed independently, as different units. Each unit has the following characteristics:•managed in a separate repository•own allocated resources (e.g. CPU and memory)•well-defined API (Application Programming Interface) for connection to other units•implemented using the programming language of choice•released using its own binaryNow, let's imagine the team develops a booking application using a microservice approach.
In this case, the UI remains the website that the user interacts with. However, the business logic is split into smaller, independent units, such as login, payment, confirmation, and many more. These units are stored in separate repositories and are written using the programming language of choice (e.g. Go for the payment service and Python for login service). To interact with other services, each unit exposes an API. And lastly, the data layer contains functions that store and retrieve customer and order data. As expected, each unit is released using its own binary.New terms•Monolith: application design where all application tiers are managed as a single unit•Microservice: application design where application tiers are managed as independent, smaller units

- There is no right way to build a software.
- If your monolithic version of the chat application needs more features when it matures you will need more resources and the project it self will get a lot difficult to manage for the developers.
- If you don't require many features then the microservice version will just waste your resources, but how will find that out.?
- There are trade-offs to both architectures which includes:

1. **Development complexity**
2. **Scalability**
3. **Time to deploy**
4. **Flexibility**
5. **Operational costs**
6. **Reliability**

---

## Development complexity

- Monoliths can only use one programming language and one source-repository which makes code handling easy but can become troublesome if the project is to complex, they are sequential in nature and offer backwards compatibility.
- Microservices can use multiple programming languages and source repositories which makes handling bigger and complex projects easier, they are concurrent and you update each function at a time.

---

## Scalability

- Monolithic applications require changes to the whole applications when they are needed to update to ensure backwards compatibility which can result in waste of resources
- Microservices are divided into small units and each unit can be upgraded separately and only uses the resources allocated to it which makes better use of our resources.

---

## Deployment

- In monoliths there is only one delivery pipeline which is used to deploy the entire stack if any error occurs while deployment the application will be offline.
- This also effects the velocity of our project.

- Using microservices you can have multiple delivery pipelines which deploy a single part of your product and are separate from one another, if one unit fails the whole application won't be offline just that specific part won't work.
- This also makes removing errors easy for developers and you can scale your application at a high velocity rate.

---

## Flexibility

- Monolithic applications are not flexible in nature, if you want to add more features or implement design changes you will have to do it for the entire stack.

- Microservices on the other hand are very flexible in nature they are basically divided into small parts and connected with each other and can be redesigned when even needed.

---

## Operational costs

- Monolithic applications have initially low costs but scaling them will be much more expensive and harder because you will have to update the entire stack.

- Microservices are expensive at first but scaling them has very low maintenance and are cheaper than monoliths in the long run. We can update each unit one by one.

---

## Reliability

- Monolithic applications are not reliable on a large scale because if one part fails the whole application will be offline.

- Microservices are small independent services connected together, even if one fails the others will still work.
- They are mostly suited for large-scale application.

- There is no perfect way to design and create an application you must first carefully analyze the trade-offs of both architectures and then decide which one is perfect for your needs.

design considerations :
requirements (who is user, what functionality is needed, how input and output will be processed)
available resources (financial condition, time frame).
If you have more resources and engineers microservice is easy to adopt
else monolith will help develop the product faster.
Monoliths

- same language
- single repository
  Microservices
- choice of programing language for each service
- seprate repository
- every service is packaged seprately
- communication through api
- seprate resources for each service
  Trade offs
- developmnt complexity
  - Monolith
    - one language
    - one repository
    - Sequential development
    - Replicates whole stack under load
    - over consumption under load
    - one delivery pipeline
    - Entire stack is deployed at once
    - low flexibilty
    - low initial cost
    - high cost at scale
    - whole stack needs to be recovered
    - low visibilty
  - Micro services
    - one or more language
    - more repository
    - concurrent development
    - Replicates service under load
    - balenced consumption under load
    - More delivery pipeline
    - Every service is deployed seprately
    - high flexiilty
    - high initial cost
    - low cost at scale
    - if any error, the specific service is recovered
    - high visibilty

---

## Resources

### Video Presentations

- [What's the Difference Between Monolith and Microservices](https://nordicapis.com/whats-the-difference-between-monolith-and-microservices/)
- [Containers vs VMs What's the difference](https://www.youtube.com/watch?v=cjXI-yxqGTI)
- [Cloud Native Architecture: Monoliths or Microservices?](https://youtu.be/BmPnNmN9jtc), **YouTube**, _Goutham Veeramachaneni_
- [Microservices vs Monolithic Architecture](https://www.mulesoft.com/resources/api/microservices-vs-monolithic)
