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

Local coverage details might look like the following figure.
![Coverage 1st Sprint for lmvc-utils](https://raw.github.com/SEP007/resources/master/quality-metrics/testability/resources/coverage-utils-1st-sprint.jpg)

More detailed views of a class even show single uncovered lines.
![Coverage 1st Sprint for lmvc-utils](https://raw.github.com/SEP007/resources/master/quality-metrics/testability/resources/coverage-utils-1st-sprint-details.jpg)

Lastly, the coverage of a complete repository is always visible on its [readme file](https://github.com/sep007/lmvc-troba) indicated by a badge.

All this allowed for a good overview of the project's state in regard to testing.

| Project       | %     | Seconds  |
| :------------ | -----:| --------:|
| lmvc-troba    |   62% |      4.2 |
| lmvc-utils    |   80% |     1.15 |
| lmvc-modules  |    0% |        - |
| lmvc          |    0% |        - |

## State after second sprint

Changes were made in the lmvc-utils and lmvc-modules project both changes being testable. Anyhow, as parts of lmvc moved to lmvc-utils problems within testing them came about. Established in the fact of code expecting to be run within the context of a web server which is not the case in a testing scenario using PHPUnit. Furtheron, the web server's context could not be emulated or mocked. All leading to the decision of not adjusting and testing the old existing code.

As a new lmvc-module taking over tasks in rendering the interface about 10 test-cases were written. All not testing the correctness of the templating-parser itself but the infrastructure setup to access them easily in a uniform way.

The lmvc-utils logger got a new scribe logging into the DevTools of Google Chrome, this also required a new formatter.

The following code coverages only deal with parts of the libraries affected by testing, omiting the old, untouched ones.

| Project       | %     | Seconds  |
| :------------ | -----:| --------:|
| lmvc-troba    |   62% |      4.2 |
| lmvc-utils    |   82% |     1.19 |
| lmvc-modules  |   72% |    0.265 |
| lmvc          |    0% |        - |

## State after third sprint

The third sprint mostly contained UI related changes and only a minor addition to the lmvc-utils project. Furthermore a new module for translations was introduced to the lmvc-modules project but has not been tested so far. Hence, code coverage and test execution time almost did not change.

| Project       | %     | Seconds  |
| :------------ | -----:| --------:|
| lmvc-troba    |   62% |      4.2 |
| lmvc-utils    |   83% |     1.23 |
| lmvc-modules  |   71% |    0.285 |
| lmvc          |    0% |        - |
