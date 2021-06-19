# Kubectl Commands

Kubectl provides a rich set of actions that can be used to interact, manage, and configure Kubernetes resources. Below is a list of handy kubectl commands used in practice.

Note: In the following commands the following arguments are used:

RESOURCE is the Kubernetes resource type
NAME sets the name of the resource
FLAGS are used to provide extra configuration
PARAMS are used to provide the required configuration to the resource

Create Resources

<p>To create resources, use the following command:</p>
<pre><code class="lang-yaml">kubectl create RESOURCE NAME [FLAGS]
</code></pre>
<h4 id="describe-resources">Describe Resources</h4>
<p>To describe resources, use the following command:</p>
<pre><code class="lang-yaml">kubectl describe RESOURCE NAME 
</code></pre>
<h4 id="get-resources">Get Resources</h4>
<p>To get resources, use the following command, where <code>-o yaml</code> instructs that the result should be YAML formated. </p>
<pre><code class="lang-yaml">kubectl get RESOURCE NAME [-o yaml]
</code></pre>
<h4 id="edit-resources">Edit Resources</h4>
<p>To edit resources, use the following command, where <code>-o yaml</code> instructs that the edit should be YAML formated. </p>
<pre><code class="lang-yaml">kubectl edit RESOURCE NAME [-o yaml]
</code></pre>
<h4 id="label-resources">Label Resources</h4>
<p>To label resources, use the following command:</p>
<pre><code class="lang-yaml">kubectl label RESOURCE NAME [PARAMS]
</code></pre>
<h4 id="port-forward-to-resources">Port-forward to Resources</h4>
<p>To access resources through port-forward, use the following command:</p>
<pre><code class="lang-yaml">kubectl port-forward RESOURCE/NAME [PARAMS]
</code></pre>
<h4 id="logs-from-resources">Logs from Resources</h4>
<p>To access logs from a resource, use the following command:</p>
<pre><code class="lang-yaml">kubectl logs RESOURCE/NAME [FLAGS]
</code></pre>
<h4 id="delete-resources">Delete Resources</h4>
<p>To delete resources, use the following command:</p>
<pre><code class="lang-yaml">kubectl delete RESOURCE NAME
</code></pre>
</div></div>
