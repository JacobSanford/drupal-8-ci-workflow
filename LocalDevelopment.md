# Local development
The goals at the outset of this project related to local development were:

 * Local development instances that approach parity with production instances.
 * Minimal workstation local tool installation.
 * A workflow that required as little knowledge of Docker / underlying tools as possible.
 * Extremely quick 'bare to dev' times.

## Dockworker
To that end, we developed Dockworker :

https://github.com/unb-libraries/dockworker

Dockworker is a series of RoboPHP commands that simplifies the local deployment process, particularly with Drupal. Local development of an instance can begin quickly and with almost no dependency installation - try it yourself with one of our live sites:

![Dockworker Startup](img/dockworker-startup.gif "Dockworker Startup")

```
> git clone git://github.com/unb-libraries/unbherbarium.lib.unb.ca.git unbherbarium.lib.unb.ca
> cd unbherbarium.lib.unb.ca
> composer install --prefer-dist
> vendor/bin/dockworker instance:start-over
```

And you're developing! To get a list of available dockworker commands:

```
vendor/bin/dockworker
```
