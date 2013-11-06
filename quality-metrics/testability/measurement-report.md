# Testability of the Patat and its dependencies

## Introduction

Testability of an application is quite general term which scope should be clarified to narrow down the objectives for this quality metric.

The Object Relational Mapper (ORM) is already partially tested using a framework called [PHPUnit](http://phpunit.de/manual/current/en/index.html) which is most commonly used testing framework used in PHP development. Still, other testing frameworks have been taken into account such as [Behat](http://behat.org) which is a Behavior Driven Development (BDD) testing framework allowing to write specs which later translate into test cases.
Anyhow, PHPUnit was chosen due to the wide acceptance and for compliance with the existing testing solution chosen for lmvc-troba.

Still, there remained a need for setting everything up homogeneous among all projects. Also including code coverage analysis which is the main metric of this quality attribute. Furthermore, it was decided to integrate with [TravisCI](http://travis-ci.org) as a continuos integration service. All projects had to be configured so that TravisCI on a new commit always pulls down the latest source, builds and tests it while reporting the result back to the developer.

All of this is integrated into development in GitHub such that members can see the status of pull requests of their features while working on them. The generation of a coverage report on every test run helps to spot untested code blocks or even failing builds.

## The initial state

When starting with the project only lmvc-troba was tested with an coverage of roughly 60% which is why it has been decided to try to comply with that medium coverage ratio.
Still, the testing setup was not build to be integrated with TravisCI and not replicatable in regards to other projects.
All of which embodied tasks to be solved within the first sprint and even before.

## State after first sprint

Every project has been setup to have a dependency to PHPUnit with a sample [configuration](https://github.com/SEP007/lmvc-troba/blob/master/tests/phpunit.xml) automatically generating code coverage metrics. Futhermore, every project has been [integrated with TravisCI](https://github.com/SEP007/lmvc-modules/blob/master/.travis.yml) which builds to every push to GitHub as intended. As an addition, every change to a repository is reported back to the chat service HipChat. This includes a warning whenever the coverage drops more than 5% by a change. Build details are available on [TracisCI's homepage](https://travis-ci.org/SEP007/lmvc-modules/builds) for every push's latest commit.



