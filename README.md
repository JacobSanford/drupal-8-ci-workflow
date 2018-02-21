# Our Drupal 8 Open, CI Workflow
## Small Team, Big Tools

## Introduction
In 2010, while participating in a usual morning of manual Drupal module updates, a colleague at [UNB Libraries](https://www.lib.unb.ca/) named [Kassim Machioudi](https://github.com/kaschioudi) suggested:

> Imagine if we only needed to change a version number in a metadata file to push all of these updates?

At the time, that idea seemed like a far-off dream. We were a small team, running many multisite and standalone instances of Drupal 6 and 5 across multiple servers. Module and core updates were painful - we received individual module update notifications for each site separately, and the update process consisted of extracting module and core tarballs on top of the existing live Drupal tree.

Most of the source of our pain, however, wasn't from the labour of doing the updates themselves - rather the problems that arose from doing the updates. When something went wrong, it **went very wrong** - we had no dev server, rollbacks were achieved only from nightly tape backups, and our local development environments were (at best) XAMP/Local Apache, and (usually) the live server itself.

## Necessary Changes
Although updates were a clear pain point, there were other pain points as well - most stemming from the the organic evolution of how we originally adopted and worked with Drupal. It wasn't that our workflow was broken - rather that we really had not thought about workflow at all. We were highly motivated to change that. We needed a to improve.

For the sake of brevity, a detailed history of the changes we made is not included in this main document. If you are interested, the steps we took and tools we adopted in the following 8 years is outlined in the [Meandering History of Tools](MeanderingHistoryOfTools.md).

## Goals
Several goals were proposed for the new workflow:

### General Goals
 * Multiple deployment environments - beginning with staging and production.
 * Synchronized branches - merges/rebases pushed upstream through environments.
 * Public lean instance repositories (where possible) with secrets stored in orchestration layer
 * Track upstream libraries through metadata only, avoid tracking then in VCS.
 * Two layers of testing - Behat and Unit Tests.

### Developer Experience
 * Local development instances that approach parity with production deployment.
 * Minimal workstation local tool installation and simple initial deployment
 * Near transparent development and workflow for developers, requiring as little knowledge of Docker / tools as possible.

## The Components
* [Lean Repository](LeanRepository.md)
* [Docker](Docker.md)
* [Docker Base Image](BaseImage.md)
* [DockWorker](DockWorker.md)
* [CargoDock](CargoDock.md)
* [Travis](Travis.md)
* [Jenkins](Jenkins.md)
* [Kubernetes](Kubernetes.md)

## Specific Cases
* [What Happens When a Commit Is Pushed?](CommitFallout.md)
