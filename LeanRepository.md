# The Lean Repository

![The Lean Repository](img/lean-repo.png "The Lean Repository")

The Lean Instance Repository serves as the keystone of our workflow. Using a Lean Repository is certainly not our novel idea - many of the major hosts and providers have their own differing formats

 * Pantheon - [Pantheon Git Repository](https://pantheon.io/docs/code/)
 * Platform.sh - [Drupal 8 Format](https://docs.platform.sh/frameworks/drupal8.html)
 * Acquia - [BLT](https://github.com/acquia/blt)

By understanding and borrowing from some of these formats (as well as introducing new features), our lean repository has evolved into a entity that contains all the information and data necessary to build an instance.

(Example : [unbherbarium.lib.unb.ca](https://github.com/unb-libraries/unbherbarium.lib.unb.ca))

```
.
├── build
│   ├── composer.json
│   ├── profile
│   └── settings
├── config-yml
├── custom
│   ├── modules
│   └── themes
├── env
├── package-conf
├── scripts
├── tests
│   ├── backstop
│   │   ├── dev
│   │   └── prod
│   └── behat
│       ├── behat.yml
│       ├── composer.json
│       └── features
├── composer.json
├── docker-compose.yml
├── docker-compose.yml.travis
├── Dockerfile
├── dockworker.yml
└── README.md
```

## Some Specifics:
 * ```build```: Version metadata for all upstream projects and libraries, including Drupal core and contrib modules
 * ```config-yml```:
 * ```custom```: Custom modules, themes and install profiles created for the instance
 * ```env```: Environment variables for Docker/Jenkins
 * ```package-conf```: Configuration for daemons used to serve the instance
 * ```tests```: Tests (Behat, Visual Regression) for the instance
 * Frameworks and structures required to bootstrap the project locally and in a testing environment
 * Codification of settings and differences between environments : local, stage, prod.
 * Source data used to build sample content
