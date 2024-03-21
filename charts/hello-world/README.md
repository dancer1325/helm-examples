# Hello World

# How to run it?
* `helm install hello ./hello-world/`
  * `kubectl get all` to check that all has been installed properly

# How to check that it's packaged into a Chart Archive?
* `helm package hello-world`
  * generates a '....tgz' == tarred
* `file hello-world-0.1.0.tgz`
  * returns that it's gzip compressed data == gzipped
* sign it -- TODO: --
