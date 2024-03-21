# Helm Example Repository
* Helm repository for example charts

## How to run it?
* Add this repository to Helm
  * `helm repo add examples https://helm.github.io/examples`
    * TODO: Why does that URL is valid? Which criteria are necessaries? WHy not 'https://github.com/dancer1325/helm-examples'
* Install an example
  * `helm install ahoy examples/hello-world`
    * 'NOTES.txt' is the output
    * `kubectl get all` to check all the packaged resources have been installed
