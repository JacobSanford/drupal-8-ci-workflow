# Local development
It is desirable to have Local development as closely similar to production as possible.

## Local MySQL server
docker-compose.yml

## Dockworker

https://github.com/unb-libraries/dockworker

Dockworker is a custom library that provides a series of RoboPHP commands which simplify the local deployment process for developers. Development on an instanct starts very quickly - try it yourself:

```
> git clone git://github.com/unb-libraries/unbherbarium.lib.unb.ca.git unbherbarium.lib.unb.ca
> cd unbherbarium.lib.unb.ca
> composer install
> dockworker instance:start
```
