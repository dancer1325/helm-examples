# Helm Example Repository
* Helm repository for example charts
## Prerequisites
* Locally or cluster you fully control (=== configure control plane), where you can
  * Run some docker daemon
    * [Docker desktop](https://www.docker.com/products/docker-desktop/)
  * Install some local cluster
    * tool
      * [minikube](https://minikube.sigs.k8s.io/docs/start/)
      * [kind](https://kind.sigs.k8s.io/)
  * Run a local cluster
    * [minikube]  `minikube start`
    * [kind] `kind create cluster`

# How to run it?
* Add this repository to Helm
  * `helm repo add examples https://helm.github.io/examples`
    * You are installing the helm chart existing in that repository NOT the helm chart under this current repo!!!
    * TODO: Why does that URL is valid? Which criteria are necessaries? WHy not 'https://github.com/dancer1325/helm-examples'
* Install it
  * `helm install ahoy examples/hello-world`
    * 'NOTES.txt' is the output
    * `kubectl get all` to check all the packaged resources have been installed

# How to uninstall?
* `helm uninstall ahoy`

# Release
* `helm install hi hello-world` & `helm install hii hello-world`
  * `helm list` to check all the releases installed
  * `helm status hii` to check the status of the release

# Helm config
* Execute the commands of 'Release'
* `kubectl get secrets` to check the Kubernetes Secrets created each time a release exists
* `kubectl get secret/SecretName -o json` to check the data with key 'release'

# Release Number
* `helm upgrade hii hello-world`
  * `helm list` to check that a new release number has been created

# `helm rollback`
* `helm install simple simple`
  * `helm list` & `kubectl get pods` to check that the name of the pod is 'simple-1'
* `helm upgrade --set name=simple-2 simple simple`
  * `helm list` to check that a new release of chart has been created
  * `kubectl get pods` to check that the name of the pod is 'simple-2'
* `helm rollback`
  * `helm list` to check that a new release has been created
  * `kubectl get pods` to check that the name of the pod is 'simple-1' again

# Chart Repository / Repo
* `helm repo list` to list chart repositories

# Values
* `helm install simple simple`
  * `kubectl get pods` to check that podName is 'simple' -> 'Values.yaml' used by default
* ways to pass customized values
  * `-f otherValue.yaml`
    * `helm upgrade -f simple/customValues.yaml simple simple` & `kubectl get all` to check that podName is now 'simple-custom'
    * `helm uninstall simple` & `helm install -f simple/customValues.yaml simple simple` & `kubectl get all` to check that podName is now 'simple-custom'
  * `--set key=vale`
    * `helm upgrade --set name=simple-upgrade simple simple` & `kubectl get all` to check that podName is now 'simple-upgrade'
