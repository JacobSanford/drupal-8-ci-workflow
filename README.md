# Our Drupal 8 CI Workflow
## Small Team, Big Tools

![Drupal 8 CI Workflow](img/logos.png "Drupal 8 CI Workflow")

## Introduction
In 2010, amid a usual morning of manual Drupal module updates, a colleague at [UNB Libraries](https://www.lib.unb.ca/), [Kassim Machioudi](https://github.com/kaschioudi) suggested:

> Imagine if we only needed to change a version number in a metadata file to push all of these updates?

At the time, that idea seemed like a far-off dream. We were a small team, running many multisite and standalone instances of Drupal 5/6 across multiple servers. Drush make was not the stable solution it later became. Composer had not yet been released. For our team, module and core updates were painful - our update process consisted of extracting module and core tarballs on top of the existing live Drupal tree.

Most of the source of our pain, however, wasn't from the labour of doing the updates themselves - rather the problems that arose from doing the updates. When something went wrong, it **went very wrong** - we had no dev server, rollbacks were achieved only from nightly tape backups, and our local development environments were (at best) XAMP/Local Apache, and (usually) the live server itself.

## Necessary Changes
Although version updates were a clear pain point, there were other pain points as well - most stemming from the the organic evolution of how we originally adopted and worked with Drupal. It wasn't that our workflow was broken - rather that we really had not designed a workflow at all. We were highly motivated to change that. We needed a to improve.

For the sake of brevity, a detailed history of the changes we made is not included in this main document. If you are interested in such things, the steps we took and tools we adopted in the following 8 years is outlined in the [Meandering History of Tools](MeanderingHistoryOfTools.md).

## Goals
Great projects begin with defined goals. After a lengthy discussion, we proposed some blue-sky goals for the new workflow:

### General

 * MIT Licensed, open lean instance repositories. Anyone can deploy and bring up our applications.
 * Track upstream libraries in metadata only, not in lean repositories.
 * Three layers of instance testing : Unit, Behat and Visual Regression Tests.

### Code

* Deployment environments defined by branches - beginning with dev and production.
* Synchronized branches - commits rebased upstream through environments.

### Deployment

 * Instances tested automatically prior to deployment.
 * Secrets stored in orchestration layer.

### Developer Experience

 * Local development instances that approach parity with production instances.
 * Minimal local development tool installation.
 * A developer workflow that requires as little knowledge of Docker / underlying tools as possible.
 * Lightning fast local development kickstarts.

## The Components
In-depth documents focused on each each component can be found on the following pages:
 * [Lean Instance Repository](LeanRepository.md)
 * [Base Docker Image](BaseImage.md)
 * [CargoDock](CargoDock.md)
 * [Travis](Travis.md)
 * [Jenkins](Jenkins.md)
 * [Kubernetes](Kubernetes.md)
 * Testing:
     * [Unit Tests](testing/UnitTests.md)
     * [Behat Tests](testing/Behat.md)
     * [Visual Regression Tests](testing/VisualRegression.md)
 * [Local Development](LocalDevelopment.md)
 * [Drupalista](Drupalista.md)

## Workflow Topics
 * [What Happens When a Commit Is Pushed?](CommitFallout.md)

## Contributors
 * [Jacob Sanford](LeanRepository.md)
 * [Brian Cassidy](Docker.md)
 * [Jeremy McDermott](BaseImage.md)
