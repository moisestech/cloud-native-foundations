# Edge Case

## Edge Case: Push and Pull methodologies for CI/CD

### Summary 2

- Within the CI/CD ecosystem, tools have a variate level of capabilities that offer the deployment of an application to production environments.

  - At a high level, these tools are using a push-based or pull-based model to release new features.

- Let's explore each CI/CD model in more detail!

### Push-based CI/CD

1. In a push-based model, as shown in the image below, the developer commits new code to the Git repository (1),
2. which triggers the Continuous Integration stages (2).
3. The code is packaged and distributed using an image registry, such as DockerHub (3).
4. The Continuous Delivery stage is triggered once the YAML manifests are updated to reference the new image tag (4).
5. A Continuous Delivery tool then pushed the updated manifests to multiple clusters (5).

### Flow diagram showcasing how the push-based CI/CD model works

### Push-based CI/CD workflow

- This model is fully operational and many tools within the ecosystem offer this deployment approach, e.g. Jenkins and CircleCI
  - However, there is one downside to this model: changes should be actively propagated to all environments.
  - If this is not fulfilled, a scenario might be reached where multiple changes need to be deployed to production, which increases the failure rate and complicated the recovery procedures.
  - Hence, wide awareness is required of features pushed to a production environment.

### Pull-based CI/CD

- In a pull-based CI/CD approach, the release process is still be triggered by a developer that pushed new features to the source code (1).
- The package (2) of the application is similar, resulting in a new image stored in DockerHub (3).
- However, once the YAML manifests are updated with the new image tag, a pull-based Continuous Delivery tool identifies new changes (4) and applies them to a Kubernetes cluster (5).
- As a result, this simplifies the process of application release, as new features can be applied automatically as soon as they are available.
- Tools that offer this CI/CD model are ArgoCD and Flux.

### Flow diagram showcasing how the pull-based CI/CD model works

### Pull-based CI/CD workflow

- It is paramount to build a deployment pipeline that fits the business requirements closely and automates the release process.
- There is no "golden path" that would cover all engineering requirements.
- However, the pull and push-based CI/CD tools contribute to the ultimate goal to ships code securely, automatically, and reliably.

---

## Related Foam Links

- [[_cd]]
