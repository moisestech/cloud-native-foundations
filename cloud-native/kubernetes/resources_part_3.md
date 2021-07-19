# Part 3

[Course Link](https://classroom.udacity.com/nanodegrees/nd064-1/parts/30cb07da-8fd4-4438-a209-b3457adb5d82/modules/7b21dfa4-aac8-4d24-82c5-65325e6dc691/lessons/d9fa86b3-301d-4966-86f8-a2f34a5a7ca3/concepts/16ba756b-e410-4536-aecb-f710f79a2ea2)

---

## Course Videos

---

## QUIZ

### QUESTION 1: Kubernetes resources are used to ensure the following functionalities?

QUESTION 1 OF 3
What Kubernetes resources are used to ensure the following functionalities?

FUNCTIONALITY

KUBERNETES RESOURCES

Application management | Deployments, ReplicaSets, and Pods

Application reachability | reac

Application configuration

Application context

Application management includes the resources that are used to deploy an application.

Application reachability includes the resources that are used to connect to an application.

Application configuration includes the resources that are used to pass configuration to an application.

Application context includes the resources that are used to provide a logical separation across applications.

### QUESTION 3:

<div class="container--3sWx1"><div class="prompt--1YMnx"><h3 class="question-number--3IlDk">Question 3 of 3</h3><div class="index-module--markdown--2MdcR ureact-markdown "><p>What kubectl commands should be used to achieve the following output?</p>
</div></div><div class="index--answer-choices--2ziSF"><div aria-label="Answer choice selections - tab through answer choices to match to concepts below. - currently ```bash
kubectl label configmap app-cm  tier=networking 
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><h3>Submit to check your answer choices!</h3></div></div><div class="index--labels--tWrVZ"><h3><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Output</p>
</div></h3><h3><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>kubectl commands</p>
</div></h3></div><div class="index--answer-selections--3mNdz"><div class="index--pair--2zqTz"><div class="index--concept--AV9z3 index--pair-part--1zw9K"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Expose the <code>backend</code> deployment using a service on port <code>7633</code></p>
</div></div><div class="index--answer-selection--bwGz3 index--pair-part--1zw9K"><div aria-label="Expose the `backend` deployment using a service on port `7633` - currently ```bash
kubectl expose deploy backend --port=7633
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><div aria-label="Answer 1, ```bash
kubectl expose deploy backend --port=7633
```." role="button" draggable="true" class="drag-item--drag-item--3sB2T" tabindex="0"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><pre><code class="lang-bash">kubectl expose deploy backend --port=7633
</code></pre>
</div></div></div></div></div><div class="index--pair--2zqTz"><div class="index--concept--AV9z3 index--pair-part--1zw9K"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Create a busybox deployment with 10 replicas, exposed on port <code>9090</code></p>
</div></div><div class="index--answer-selection--bwGz3 index--pair-part--1zw9K"><div aria-label="Create a busybox deployment with 10 replicas, exposed on port `9090` - currently ```bash
kubectl create deploy busybox \
--image=busybox -r=10 --port=9090
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><div aria-label="Answer 1, ```bash
kubectl create deploy busybox \
--image=busybox -r=10 --port=9090
```." role="button" draggable="true" tabindex="0" class="drag-item--drag-item--3sB2T"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><pre><code class="lang-bash">kubectl create deploy busybox \
--image=busybox -r=10 --port=9090
</code></pre>
</div></div></div></div></div><div class="index--pair--2zqTz"><div class="index--concept--AV9z3 index--pair-part--1zw9K"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Label a configmap with the <code>tier=networking</code> key-value pair</p>
</div></div><div class="index--answer-selection--bwGz3 index--pair-part--1zw9K"><div aria-label="Label a configmap with the `tier=networking` key-value pair - currently ```bash
kubectl label configmap app-cm  tier=networking 
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><div aria-label="Answer 1, ```bash
kubectl label configmap app-cm  tier=networking 
```." role="button" draggable="true" class="drag-item--drag-item--3sB2T" tabindex="0"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><pre><code class="lang-bash">kubectl label configmap app-cm  tier=networking 
</code></pre>
</div></div></div></div></div><div class="index--pair--2zqTz"><div class="index--concept--AV9z3 index--pair-part--1zw9K"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Delete the <code>sandbox</code> namespace</p>
</div></div><div class="index--answer-selection--bwGz3 index--pair-part--1zw9K"><div aria-label="Delete the `sandbox` namespace - currently ```bash
kubectl delete ns sandbox
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><div aria-label="Answer 1, ```bash
kubectl delete ns sandbox
```." role="button" draggable="true" class="drag-item--drag-item--3sB2T" tabindex="0"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><pre><code class="lang-bash">kubectl delete ns sandbox
</code></pre>
</div></div></div></div></div><div class="index--pair--2zqTz"><div class="index--concept--AV9z3 index--pair-part--1zw9K"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><p>Describe the secret with the name <code>team-token</code></p>
</div></div><div class="index--answer-selection--bwGz3 index--pair-part--1zw9K"><div aria-label="Describe the secret with the name `team-token` - currently ```bash
kubectl describe secret team-token
```" aria-dropeffect="move" role="listbox" tabindex="0" class="drop-zone--drop-zone--38cMu"><div aria-label="Answer 1, ```bash
kubectl describe secret team-token
```." role="button" draggable="true" class="drag-item--drag-item--3sB2T" tabindex="0"><div class="_15vzQlp3FJ8f94suLiPCPf ureact-markdown "><pre><code class="lang-bash">kubectl describe secret team-token
</code></pre>
</div></div></div></div></div></div></div>

---

## Related

- [[_resources]]
