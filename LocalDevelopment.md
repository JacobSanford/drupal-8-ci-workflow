# Local development
It is desirable to have Local development as closely similar to production as possible.

## Local MySQL server
docker-compose.yml

## Dockworker

https://github.com/unb-libraries/dockworker

Dockworker is a custom library, developed as a series of RoboPHP commands that simplifies the local deployment process, particularly with Drupal. Local development of an instance can begin quickly and with almost no dependency installation - try it yourself with one of our live sites:

```
> git clone git://github.com/unb-libraries/unbherbarium.lib.unb.ca.git unbherbarium.lib.unb.ca
> cd unbherbarium.lib.unb.ca
> composer install --prefer-dist
> vendor/bin/dockworker instance:start-over
```

To get a list of available dockworker commands:

```
vendor/bin/dockworker
```
