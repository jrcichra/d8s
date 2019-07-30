# kubernetes-paas
Dynamically provision developer workstations inside kubernetes pods

# How this would work
+ Deployment of a pod that has access to kubectl commands
+ Intercepts deployments with a specific label and spins up a "sidecar" containers inside each pod
+ Have the sidecar container expose port 22 and "attach" to the main container, passing around stdin and stdout 
+ The sidecar container would need access to the kubectl api, and use a library like: https://github.com/kubernetes-client/python/blob/master/examples/exec.py with the ability to handle exec streams.

Then in theory, you could dynamically provision ssh'able pods/containers that developers could test their code in. It would be an easy way to interact with an existing docker image just to "play around in" on a kubernetes cluster.
