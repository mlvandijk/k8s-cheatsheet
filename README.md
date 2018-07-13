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
`kubectl config get-contexts` shows the current kubectl contexts.
`kctx`shows the current kubectl contexts (active context is marked yellow).

### Creating aliases for your contexts
`kctx <alias>=<NAME>` sets an alias for your context
`kctx <alias>` - Switch to context (using alias, if you've set up an alias).
`kubectl get namespaces` shows the current namespace within the active cluster.
`kns` also shows the namespaces (active namespace for the kubectl context is marked yellow).


