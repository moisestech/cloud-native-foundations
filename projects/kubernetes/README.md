# Kubernetes Declarative Manifests

Place the Kubernetes declarative manifests in this directory.

## Lesson 3.21 Exercise

### [Kubernetes Resources](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/0832ec55-f1ca-47aa-b839-27e521051096)

Now you have learned many Kubernetes recourses, in this exercise, you will deploy the following resources using the `kubectl` command.

- a namespace

  - name: `demo`
  - label: `tier: test`

- a deployment:

  - image: `nginx:alpine`
  - name:`nginx-apline`
  - namespace: d`emo`
  - replicas: 3
  - labels: `app: nginx`, `tag: alpine`

- a service:

  - expose the above deployment on port `8111`
  - namespace: `demo`

- a configmap:
  - name: `nginx-version`
  - containing key-value pair: `version=alpine`
  - namespace: `demo`

**Note:** Nginx is one of the public Docker images, that you can access and use for your exercises or testing purposes.

---

Make sure the following tasks are completed:

[x] You have created a Namespace
[x] You have created a Deployment
[x] You have created a Service
[x] You have created a Configmap

---

### Lesson 3.22 Solution: Kubernetes Resources

Below is a snippet creating a namespace and labeling it, a deployment, a service, and a configmap using the kubectl operations.

<pre><code><span class="hljs-comment"># create the namespace </span>
<span class="hljs-comment"># note: label option is not available with `kubectl create`</span>
kubectl create ns demo

<span class="hljs-comment"># label the namespace</span>
kubectl label ns demo tier=<span class="hljs-built_in">test</span>

<span class="hljs-comment"># create the nginx-alpine deployment </span>
kubectl create deploy nginx-alpine --image=nginx:alpine  --replicas=<span class="hljs-number">3</span> --namespace demo

<span class="hljs-comment"># label the deployment</span>
kubectl label deploy nginx-alpine app=nginx tag=alpine --namespace demo

<span class="hljs-comment"># expose the nginx-alpine deployment, which will create a service</span>
kubectl expose deployment nginx-alpine --port=<span class="hljs-number">8111</span> --namespace demo

<span class="hljs-comment"># create a config map</span>
kubectl create configmap nginx-version --from-literal=version=alpine --namespace demo
</code></pre>
