# Jenkins
Instead of allowing Travis access to our Kubernetes cluster, we prefer to instead have Travis trigger a Jenkins job that deploys the newly built image to the K8s cluster.

An example of this can be seen in the [triggerKubeDeploy.sh job in CargoDock](https://github.com/unb-libraries/CargoDock/blob/master/travis/triggerKubeDeploy.sh)
