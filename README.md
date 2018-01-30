# Our Drupal 8 CI Local to Prod Workflow
## Small Team, Big Tools

### Introduction
In 2010, in the midst of a morning of manual Drupal module updates, a colleague at [UNB Libraries](https://www.lib.unb.ca/) named [Kassim Machioudi](https://github.com/kaschioudi) suggested:

> Imagine if we only needed to change a version number in a metadata file to do all of these updates?

At the time, that seemed like a far-off dream. We were running many multisite and standalone instances of Drupal 6 and 5 across multiple servers. Updates were painful - we received module update notifications individually, and for years the update process itself involved extracting tarballs on top of the existing Drupal tree.

Most of the source of update pain, however, wasn't from the technical update process itself, rather the problems that arose FROM the update. When something went wrong, it **went very wrong** - we had no dev server, rollbacks needed to come nightly tape backups, and our local development environments were no more than XAMP/Local Apache.

As Rather excitingly, We had recently adopted the use of [Drush](https://github.com/drush-ops/drush) to speed up the maintenance process.

### The Journey
Although the symptom was painful updates; the real problem was the organic evolution of how we worked with Drupal. It wasn't that our workflow was broken - we really had no workflow.



PUT HISTORY HERE. BE BRIEF!

For the first few years, we scraped together some rudimentary tools, and attempted to leverage

* http://www.aegirproject.org/

#### Deployment

Pushback
* https://github.com/unb-libraries/pushback

Local development
* Vagrant
* VirtualBox
* Chef
*


### Behold, Docker
Containerization has made all of this possible. We had previously developed [vagrants](https://github.com/unb-libraries/vagrant-ubuntu/tree/drupal) and chef recipes.


END HISTORY


### The Components

* [Lean Repository](LeanRepository.md)
* Docker
* DockWorker
* Travis
* Concourse
* Kubernetes
