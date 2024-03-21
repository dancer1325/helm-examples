# Helm Example Repository
* Helm repository for example charts

## How to run it?
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