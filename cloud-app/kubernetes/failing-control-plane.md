# Failing Control Plane

## Edge Case: Failing Control Plane for Kubernetes

🎥 [Udacity, Video Link](https://www.youtube.com/watch?v=J3avoSaPzZ4)

---

## Summary

Failure is expected in any technology stack. However, it is more important to have efficient remediations steps rather than plan for no-failure scenarios. Kubernetes provides methods to handle some of the low-level failures and ensure the application is healthy and accessible. Some of these resources are:

<ul>
<li>ReplicaSets - to ensure that the desired amount of replicas is up and running at all times</li>
<li>Liveness probes - to check if the pod is running, and restart it if it is in an errored state</li>
<li>Readiness probes - ensure that traffic is routed to that pods that are ready to handle requests</li>
<li>Services - to provide one entry point to all the available pods of an application</li>
</ul>
<p>These services, prompt the automatic recovery of an application if an error is encountered. However, failure can happen at the cluster-level, for example, a control plane failure. In this case, a subset or all control plane components are compromised. While the situation is disastrous, the applications are still running and handling traffic.  The downside of the control plane failure is that no new workloads can be deployed and no changes can be applied to the existing workloads.</p>
<p>The engineering team needs to recover the control plane components as a critical priority. However, they should not worry about recovering applications, as these will be intact and still handling requests. </p>

---

- [[_kubernetes]]
