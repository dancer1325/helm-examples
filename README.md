# Helm Example Repository
* Helm repository for example charts

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
