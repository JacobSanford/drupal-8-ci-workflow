# Jenkins
Instead of allowing Travis access to our Kubernetes cluster, we prefer to instead have Travis trigger a Jenkins job that deploys the newly built image to the K8s cluster.
