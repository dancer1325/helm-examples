# How has it been created?
* `helm create withdependencies`

# How to run it?
* `helm dependency build ./withdependencies`
  * download the required dependencies
* `helm install with ./withdependencies`
  * `kubectl get all` to check that all has been installed properly
