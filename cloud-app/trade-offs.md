# Trade Offs

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

## Development complexity

- Monoliths can only use one programming language and one source-repository which makes code handling easy but can become troublesome if the project is to complex, they are sequential in nature and offer backwards compatibility.
- Microservices can use multiple programming languages and source repositories which makes handling bigger and complex projects easier, they are concurrent and you update each function at a time.

## Scalability

- Monolithic applications require changes to the whole applications when they are needed to update to ensure backwards compatibility which can result in waste of resources
- Microservices are divided into small units and each unit can be upgraded separately and only uses the resources allocated to it which makes better use of our resources.

## Deployment

- In monoliths there is only one delivery pipeline which is used to deploy the entire stack if any error occurs while deployment the application will be offline.
- This also effects the velocity of our project.

- Using microservices you can have multiple delivery pipelines which deploy a single part of your product and are separate from one another, if one unit fails the whole application won't be offline just that specific part won't work.
- This also makes removing errors easy for developers and you can scale your application at a high velocity rate.

## Flexibility

- Monolithic applications are not flexible in nature, if you want to add more features or implement design changes you will have to do it for the entire stack.

- Microservices on the other hand are very flexible in nature they are basically divided into small parts and connected with each other and can be redesigned when even needed.

## Operational costs

- Monolithic applications have initially low costs but scaling them will be much more expensive and harder because you will have to update the entire stack.

- Microservices are expensive at first but scaling them has very low maintenance and are cheaper than monoliths in the long run. We can update each unit one by one.

## Reliability

- Monolithic applications are not reliable on a large scale because if one part fails the whole application will be offline.

- Microservices are small independent services connected together, even if one fails the others will still work.
- They are mostly suited for large-scale application.

- There is no perfect way to design and create an application you must first carefully analyze the trade-offs of both architectures and then decide which one is perfect for your needs.

---

## Resources

### Video Presentations

- [What's the Difference Between Monolith and Microservices](https://nordicapis.com/whats-the-difference-between-monolith-and-microservices/)
- [Containers vs VMs What's the difference](https://www.youtube.com/watch?v=cjXI-yxqGTI)
- [Cloud Native Architecture: Monoliths or Microservices?](https://youtu.be/BmPnNmN9jtc), _Goutham Veeramachaneni_, YouTube
