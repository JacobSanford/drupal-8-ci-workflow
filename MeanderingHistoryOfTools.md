# The Toolsets Along Our Journey

This document is incomplete and poorly structured!

Rather excitingly, We had recently adopted the use of [Drush](https://github.com/drush-ops/drush) to speed up the maintenance process.

For the first few years, we scraped together some rudimentary tools, and attempted to leverage

* http://www.aegirproject.org/

#### Deployment

Pushback
* https://github.com/unb-libraries/pushback

Local development
* Vagrant
* VirtualBox
* Chef

### Behold, Docker
Containerization changed our world. We had previously developed [vagrants](https://github.com/unb-libraries/vagrant-ubuntu/tree/drupal) and chef recipes.

For all the problems they solved, they also create new challenges:
 * Where do they run? What starts them?
 * How do we route traffic to them? All on different ports / load balancer?
 * How do we monitor containers? How do they talk to each other? MySQL / Drupal
 * Where does persistent storage live? Storing data on host is not scalable. How do we mount it?
 * Etc.

Additionally:

* We can (and did) build and design some tools to meet these challenges, but these are not novel problems. We were not working with the community.
* CoreOS had Fleet. This was basic and met most of our requirements, but sacrificed scalability and portability. That was OK for us.
* Fleet is dead. Kubernetes to the rescue.
