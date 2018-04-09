# Jenkins
Jenkins triggers deployment to various environments once the instances have been built and tested.

## Deployment
Instead of allowing Travis access to our Kubernetes cluster, we prefer to instead have Travis trigger a Jenkins job (on success) that deploys the newly built image to the K8s cluster. This avoids exposing deployment specifics and credentials outside our local environment (Aside from Jenkins keys).

An example of this can be seen in the [triggerKubeDeploy.sh job in CargoDock](https://github.com/unb-libraries/CargoDock/blob/master/travis/triggerKubeDeploy.sh)
