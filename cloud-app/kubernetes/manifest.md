# Manifest

## Declarative Kubernetes Manifests

### Summary

Kubernetes is widely known for its support for imperative and declarative management techniques. The **imperative** approach enables the management of resources using kubectl commands directly on the live cluster. For example, all the commands you have practiced so far (e.g. kubectl create deploy [...]) are using the imperative approach. This technique is best suited for development stages only, as it presents a low entry-level bar to interact with the ClusterIP.

On the other side, the **declarative** approach uses manifests stored locally to create and manage Kubertenest objects. This approach is recommended for production releases, as we can version control the state of the deployed resources. However, this technique presents a high learning curve, as an in-depth understanding of the YAML manifest structure is required. Additionally, using YAML manifests unlocks the possibility of configuring more advanced options, such as volume mounts, readiness and liveness probes, etc.

---

## YAML Manifest structure

A YAML manifest consists of 4 obligatory sections:

- **apiversion** - API version used to create a Kubernetes object
- **kind**- object type to be created or configured
- **metadata** - stores data that makes the object identifiable, such as its name, namespace, and labels
- **spec** - defines the desired configuration state of the resource

To get the YAML manifest of any resource within the cluster, use the <code>kubectl get</code> command, associated with the <code>-o yaml</code> flag, which requests the output in YAML format. Additionally, to explore all configurable parameters for a resource it is highly recommended to reference the official <a target="_blank" href="https://kubernetes.io/docs/home/">Kubernetes documentation</a>

---

## Deployment YAML manifest

In addition to the required sections of a YAML manifest, a Deployment resource covers the configuration of ReplicaSet, RollingOut strategy, and containers. Bellow is a full manifest of a Deployment explaining each parameter:

<pre><code class="lang-yaml">## Set the API endpoint used to create the Deployment resource.
apiVersion: apps/v1
## Define the type of the resource.
kind: Deployment
## Set the parameters that make the object identifiable, such as its name, namespace, and labels.
metadata:
  annotations:
  labels:
    app: go-helloworld
  name: go-helloworld
  namespace: default
## Define the desired configuration for the Deployment resource.
spec:
  ## Set the number of replicas.
  ## This will create a ReplicaSet that will manage 3 pods of the Go hello-world application.
  replicas: 3
  ## Identify the pods managed by this Deployment using the following selectors.
  ## In this case, all pods with the label `go-helloworld`.
  selector:
    matchLabels:
      app: go-helloworld
  ## Set the RollingOut strategy for the Deployment.
  ## For example, roll out only 25% of the new pods at a time.
  strategy:
    rollingUpdate:
      maxSurge: 25%
      maxUnavailable: 25%
    type: RollingUpdate
  ## Set the configuration for the pods.
  template:
    ## Define the identifiable metadata for the pods.
    ## For example, all pods should have the label `go-helloworld`
    metadata:
      labels:
        app: go-helloworld
    ## Define the desired state of the pod configuration.
    spec:
      containers:
        ## Set the image to be executed inside the container and image pull policy
        ## In this case, run the `go-helloworld` application in version v2.0.0 and
        ## only pull the image if it's not available on the current host.
      - image: pixelpotato/go-helloworld:v2.0.0
        imagePullPolicy: IfNotPresent
        name: go-helloworld
        ## Expose the port the container is listening on.
        ## For example, exposing the application port 6112 via TCP.
        ports:
        - containerPort: 6112
          protocol: TCP
        ## Define the rules for the liveness probes.
        ## For example, verify the application on the main route `/`,
        ## on application port 6112. If the application is not responsive, then the pod will be restarted automatically. 
        livenessProbe:
           httpGet:
             path: /
             port: 6112
        ## Define the rules for the readiness probes.
        ## For example, verify the application on the main route `/`,
        ## on application port 6112. If the application is responsive, then traffic will be sent to this pod.
        readinessProbe:
           httpGet:
             path: /
             port: 6112
        ## Set the resource requests and limits for an application.
        resources:
        ## The resource requests guarantees that the desired amount 
        ## CPU and memory is allocated for a pod. In this example, 
        ## the pod will be allocated with 64 Mebibytes and 250 miliCPUs.
          requests:
            memory: "64Mi"
            cpu: "250m"
        ## The resource limits ensure that the application is not consuming 
        ## more than the specified CPU and memory values. In this example, 
        ## the pod will not surpass 128 Mebibytes and 500 miliCPUs.
          limits:
            memory: "128Mi"
            cpu: "500m"
</code></pre>

---

## Service YAML manifests

In addition to the required sections of a YAML manifest, a Service resource covers the configuration of service type and ports the service should configure. Bellow is a full manifest of a Service explaining each parameter:

<pre><code class="lang-yaml">
<span class="hljs-comment">## Set the API endpoint used to create the Service resource.</span>
apiVersion: v1
<span class="hljs-comment">## Define the type of the resource.</span>
kind: Service
<span class="hljs-comment">## Set the parameters that make the object identifiable, such as its name, namespace, and labels.</span>
metadata:
  labels:
    app: go-helloworld
  name: go-helloworld
  namespace: default
<span class="hljs-comment">## Define the desired configuration for the Service resource.</span>
spec:
  <span class="hljs-comment">## Define the ports that the service should serve on.</span>
  <span class="hljs-comment">## For example, the service is exposed on port 8111, and</span>
  <span class="hljs-comment">## directs the traffic to the pods on port 6112, using TCP.</span>
  ports:
  - port: 8111
    protocol: TCP
    targetPort: 6112
  <span class="hljs-comment">## Identify the pods managed by this Service using the following selectors.</span>
  <span class="hljs-comment">## In this case, all pods with the label `go-helloworld`.</span>
  selector:
    app: go-helloworld
  <span class="hljs-comment">## Define the Service type, here set to ClusterIP.</span>
  type: ClusterIP
</code></pre>

---

## Useful command

Kubernetes YAML manifests can be created using the <code>kubectl apply</code> command, with the following syntax:

<pre><code class="lang-bash"><span class="hljs-comment"># create a resource defined in the YAML manifests with the name manifest.yaml</span>
kubectl apply <span class="hljs-operator">-f</span> manifest.yaml
</code></pre>

To delete a resource using a YAML manifest, the <code>kubectl delete</code> command, with the following syntax:

<pre><code class="lang-bash"><span class="hljs-comment"># delete a resource defined in the YAML manifests with the name manifest.yaml</span>
kubectl delete <span class="hljs-operator">-f</span> manifest.yaml
</code></pre>

Kubernetes documentation is the best place to explore the available parameters for YAML manifests. However, a support YAML template can be constructed using kubectl commands. This is possible by using the <code>--dry-run=client</code> and <code>-o yaml</code>flags which instructs that the command should be evaluated on the client-side only and output the result in YAML format.

<pre><code class="lang-bash"><span class="hljs-comment"># get YAML template for a resource </span>
kubectl create RESOURCE [REQUIRED FLAGS] --dry-run=client -o yaml
</code></pre>

For example, to get the template for a Deployment resource, we need to use the create command, pass the required parameters, and associated with the <code>--dry-run</code> and <code>-o yaml</code> flags. This outputs the base template, which can be used further for more advanced configuration.

<pre><code class="lang-bash"><span class="hljs-comment"># get the base YAML templated for a demo Deployment running a nxing application</span>
 kubectl create deploy demo --image=nginx --dry-run=client -o yaml
</code></pre>

---

## Declarative Kubernetes Manifests Walkthrough

<div class="_main--content-container--ILkoI"><div><div class="index--container--2OwOl"><div class="index--atom--lmAIo layout--content--3Smmq"><div class="ltr"><div class="index-module--markdown--2MdcR ureact-markdown "><h1 id="solution-declarative-kubernetes-manifests">Solution: Declarative Kubernetes Manifests</h1>
</div></div><span></span></div></div></div><div><div class="index--container--2OwOl"><div class="index--atom--lmAIo layout--content--3Smmq"><div class="ltr"><div class="index-module--markdown--2MdcR ureact-markdown "><h2 id="declarative-approach">Declarative Approach</h2>
<p>The declarative approach consists of using a full YAML definition of resources. As well, with this approach, you can perform directory level operations.</p>
<p>Examine the manifests for all of the resources in the <a target="_blank" href="https://github.com/udacity/nd064_course_1/tree/main/exercises/manifests">exercises/manifests</a>.</p>
<p>To create the resources, use the following command:</p>
<pre><code>kubectl apply <span class="hljs-operator">-f</span> exercises/manifests/
</code></pre><p>To inspect all the resources within the namespace, use the following command:</p>
<pre><code class="lang-bash">kubectl get all -n demo

NAME READY STATUS RESTARTS AGE
pod/nginx-alpine-798fb5b8bb-8rzq9 1/1 Running 0 12s
pod/nginx-alpine-798fb5b8bb-ms28l 1/1 Running 0 12s
pod/nginx-alpine-798fb5b8bb-qgqb2 1/1 Running 0 12s

NAME TYPE CLUSTER-IP EXTERNAL-IP PORT(S) AGE
service/nginx-alpine ClusterIP 10.109.197.180 &lt;none&gt; 8111/TCP 18s

NAME READY UP-TO-DATE AVAILABLE AGE
deployment.apps/nginx-alpine 3/3 3 3 12s

NAME DESIRED CURRENT READY AGE
replicaset.apps/nginx-alpine-798fb5b8bb 3 3 3 12s
</code></pre>

---

## Manifest Summary

This demo showcases how a Namespace and Deployment resource can be deployed using YAML manifests.

## New terms

**Imperative configuration** - resource management technique, that operates and interacts directly with the live objects within the cluster.
**Declarative configuration** - resource management technique, that operates and manages resources using YAML manifests stored locally.

## Further reading

Explore more details about different management techniques and advanced configuration for Deployment resources:

- [Managing Kubernetes Objects Using Imperative Commands](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/imperative-command/), _Kubernetes_, Website
- [Declarative Management of Kubernetes Objects Using Configuration Files](https://kubernetes.io/docs/tasks/manage-kubernetes-objects/declarative-config/), _Kubernetes_, Website
- [Configure Liveness, Readiness Probes for a Deployment](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/), _Kubernetes_, Website
- [Managing Resources for Containers](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/), _Kubernetes_, Website
