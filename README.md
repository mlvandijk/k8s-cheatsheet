# Cheatsheet for Google Cloud and Kubernetes

## Install gcloud
Google cloud SDK with the kubectl component:
```
brew update
brew cask install google-cloud-sdk
gcloud auth login
gcloud init
gcloud components install kubectl
```
## CLI tools
`brew install kubectx --without-kubernetes-cli --with-short-names`

This gives you the `kctx` and `kns` commands.

## Kubeclt

Kubeclt (KUBErnetes ConTrL) - command line interface for Kubernetes

`kubectl version` check the version.

`kubectl config get-contexts` shows the current kubectl contexts.

`kctx`shows the current kubectl contexts (active context is marked yellow).

### Creating aliases for your contexts
`kctx <alias>=<NAME>` sets an alias for your context

`kctx <alias>` - Switch to context (using alias, if you've set up an alias).

### Name spaces
`kubectl get namespaces` shows the current namespace within the active cluster.

`kns` also shows the namespaces (active namespace for the kubectl context is marked yellow).

`kubectl get all`only shows the resources of the active namespace.

To see a different namespace use the “-n” argument: `kubectl get all -n <namespace>`

`kns <>namespace>` to switch to that namespace.

`kubectl get all` to see all resources for that namespace.

### Pods
`kubectl get pods` gets all the pods of your project namespace.

`kubectl logs <pod name>` look at the logs

`kubectl logs <pod name> -f` follow the logs (a.k.a. tail) by using the -f parameter.

`kubectl describe pod <pod name>` see relevant information about the pod.
If your pod didn’t start and you don’t have any logging then this is the place to look.

`kubectl exec -it {pod name} /bin/bash` open a SSH connection to your container. 
Note: The command will be executes on the first container of your pod; if you have multiple containers within one pod you need to specific the `-c <container name>` parameter.

`kubectl port-forward <pod name> 8888:8080` create port-forwards to your container (which is practical if you want to connect to a debug port, for instance).
In your browser you can now visit: [http://localhost:8888](http://localhost:8888).

### Kill it

`kubectl delete replicaset` delete replicaset.

`kubectl delete pod <podname>` to delete that pod.

`kubectl get pods <podname> -o yaml`

### Monitor

`kubectl get events` to monitor namespace 

# Links:

- https://s3-eu-west-1.amazonaws.com/uploads-eu.hipchat.com/111629/1090354/cSa8xm0topnMweS/6738223-dzone-refcardz-kubernetes-rc233.pdf

- https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-probes/

- https://kubernetes.io/docs/tasks/debug-application-cluster/get-shell-running-container/

- https://kubernetes.io/docs/concepts/configuration/secret/
