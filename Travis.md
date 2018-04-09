# Travis
Travis is leveraged to build and test the instance before deploying to staging. Instances building and testing on travis depend heavily on [CargoDock](CargoDock.md) to provide the build and test methods, and each repository contains only a stub [.travis.yml](https://raw.githubusercontent.com/unb-libraries/unbherbarium.lib.unb.ca/dev/.travis.yml) file:

```
services:
  - docker

php:
  - '7.1'

cache:
  directories:
        - $HOME/.composer/cache

git:
  depth: 1

env:
  global:
    - SERVICE_NAME=unbherbarium.lib.unb.ca
    - AMAZON_ECR_REGION=us-east-1
    - DEPLOY_BRANCHES=dev,prod
    - DEPLOYMENT_FINISHED_MARKER=99_report_as_complete
    - DOCKER_UPSTREAM_IMAGE=unblibraries/drupal:alpine-nginx-php7-8.x-composer
    - OLD_IMAGES_TO_KEEP=2
    - SERVICE_DEPLOY_PORT=80
    - SERVICE_TEST_UP_PATH=/user

before_install:
  - git clone git://github.com/unb-libraries/CargoDock.git CargoDock
  - CargoDock/travis/installDockerCompose.sh
  - CargoDock/aws/installAuthAws.sh
  - cp docker-compose.yml.travis docker-compose.yml
  - CargoDock/travis/setDockerComposeEnv.sh

before_script:
  - CargoDock/travis/buildInstanceTheme.sh
  - CargoDock/travis/buildInstanceForTesting.sh
  - CargoDock/travis/waitForDeploy.sh
  - CargoDock/travis/checkStartupForErrors.sh

script:
  - CargoDock/travis/testInstance.sh

after_success:
  - CargoDock/travis/buildImagePushToRepo.sh
  - CargoDock/travis/cleanupOldImages.sh
  - CargoDock/travis/triggerKubeDeploy.sh
```

An successful Travis build log [can be seen here](https://travis-ci.org/unb-libraries/unbherbarium.lib.unb.ca/builds/362701681).
