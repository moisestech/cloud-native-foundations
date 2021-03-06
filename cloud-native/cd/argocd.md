# ArgoCD

## **ArgoCD Walkthrough**

---

## **Summary**

- This demo is a walkthrough of the process of installing and accessing **ArgoCD**.

- Here are some noteworthy steps:

- Use the official **ArgoCD** install page

  - The YAML manifest for the NodePort service can be found under the **argocd**-server-nodeport.yaml file in the course repository

    - Access the **ArgoCD** UI by going to `https://192.168.50.4:30008` or `http://192.168.50.4:30007`

      - When accessing the **ArgoCD** UI, a browser SSL warning is encountered.
      - This is happening because the **ArgoCD** server is not setup with SSL certificates to authenticate the server.
      - Hence, an insecure connection is established with the server.

        - As a result, the warning prompt is encountered and you should just bypass the warning page

        - Login credentials can be retrieved using the steps in the credentials guide
        - Application Deployment
        - This demo provides a step by step guide on how to deploy an application using **ArgoCD**.

- To follow the demo closely, use the following resources:

- Python-manifests folder contains the YAML configuration for the Python hello-world application
- **argocd**-python manifest for the Application CRD to used to deploy the Python hello-world application

---

## Resources

- [Argo CD - Declarative GitOps CD for Kubernetes](https://argoproj.github.io/argo-cd/)
- [GitOps with Argo and Crossplane - Civo.com](https://www.civo.com/meetups/meetup-10)
- [Intezer - New Attacks on Kubernetes via Misconfigured Argo Workflows](https://www.intezer.com/blog/container-security/new-attacks-on-kubernetes-via-misconfigured-argo-workflows/)

---

## Foam Link

- [[_cd]]
