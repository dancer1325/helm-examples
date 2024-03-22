# How has it been created?
* `helm create softsubchart`
* `mkdir othercharts` & `cd othercharts` & `helm create other`

# How to run it?
* `helm install soft ./`
  * `kubectl get all` to check that parent chart has been installed properly
  * other subchart have NOT been installed and NOT needed!! 
    * Reason: Soft dependency
