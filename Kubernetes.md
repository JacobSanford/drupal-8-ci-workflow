# Kubernetes
Kubernetes serves as the core framework for our docker infrastructure. What is kubernetes? From https://kubernetes.io/:

> Kubernetes is an open-source system for automating deployment, scaling, and management of containerized applications. It groups containers that make up an application into
logical units for easy management and discovery.

Distilled down : Kubernetes itself is a series of docker containers that work together (often across several servers (nodes)) to orchestrate the deployment of other containers and services. These containers are known as the core Kube services.

## Components of an Application in Kubernetes
There are 4 primary components of our applications in Kubernetes:

### 1. The Docker Image
Docker containers are deployed in Kubernetes from pre-built images. We build these images in Travis (using [Cargodock](https://github.com/unb-libraries/CargoDock/tree/kubernetes)) from our [Lean Instance Repositories](LeanRepository.md) (ex: [unbherbarium.lib.unb.ca](https://github.com/unb-libraries/unbherbarium.lib.unb.ca)).

Once an image is built, it must be stored in a location that Kubernetes can access it. This storage location is known as a [Docker Registry](https://docs.docker.com/registry/). Docker Registries can be public (anyone can access the image), or private (restricted access).

Although most Lean Instance Repositories for our applications are public on GitHub, and we we go to great efforts to ensure no private data is baked into the resultant Docker images, we store the built images for **site applications** privately in Amazon's [Elastic Container Registry](https://aws.amazon.com/ecr/), a private registry. Storing the images in the AWS ECR also makes our applications much more portable - if we wish to run an application in the cloud, only small changes in the build pipeline would be necessary.

Images that are not related to site applications (i.e. the [Hodor Slack bot](https://hub.docker.com/r/jacobsanford/slack-hodor/), are stored in the public [DockerHub registry](https://hub.docker.com/).

### 2. The Kubernetes Deployment/Service Definition
Applications are represented in the Kubernetes ecosystem by Deployments and Services. One application has both a deployment and a service.

An application is asserted to the core kube services via structured YAML. The YAML file contains metadata : what Docker image to deploy, where/how to deploy it, what ports to open to the public and where to access its persistent disk store. These YAML files contain somewhat sensitive data and are stored in a private GitHub repository.

The YAML deployment/service file also defines which environment variables are exposed to the container.

### 3. The Kubernetes Ingress controller
How end users reach the deployments is controlled by the ingress.

### 4. The Persistent Disk Storage
Most applications require user data storage. Docker images are usually designed so that the user data from a service is stored on a persistent disk store (Docker Volume), while the upstream code, libraries and modules exist only for the lifetime of the container.

Volumes mounted into the container can originate from several sources, and in our case we use NFS mounts.
