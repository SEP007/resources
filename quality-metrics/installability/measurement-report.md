# Installability of the Patat

## Introduction

The Patat application being a web application lowers its installability inherently compared to native applications. Native application mostly take advantage of features offered by the platform they are running on the facilitate the installation and update process for the user. This noticable especially on mobile platforms on which frequently even accomplish and automatic update process without the user even noticing the update performed. Desktop platforms on the other hand most often require a partially automated update process facilitated by the application itself or the operating system.

Web applications are different in nature in this regard. The browser requests the latest state of the application from the server while hopefully performing some intelligent caching on non-changing resources. This process changes and shifts the focus of installability significantly. Developers are responsible for easing the steps involved in updating the system on the production server. It is advisable to automate most tasks involved and ultimativly aim at paving the way for continuos deployment.

## The initial state

The Patat application depended on three dependencies: lmvc, lmvc-troba and lmvc-modules. All taking over different but common responsibilities in web development. Dependency management was and still is accomplished by using the [composer](http://getcomposer.com) dependency manager. The tool allows migrating between dependencies' versions and automatically fetches them from [packagist](http://packagist.com) which is an endpoint in the end giving urls to repositories on [GitHub](https://github.com). After all, dependencies are defined within a `composer.json` file and will be installed into a configurable sub-directory. Moreover, composer comes with an so called autoloader automatically loading in dependencies into a class' context when required with their related namespace. This all enables setting up a quick development project, importing some dependencies and using them. Still, there are more tasks to tackle.

Installing an web application on a local or remote machine furthermore requires an application stack fulfilling the application's demands. For Patat this is a normal AMP-stack including an Apache server, an MySQL database and a PHP runtime. This stack for one can be installed manually on almost any system, for another pre-build packages make it easier to climb that hill. The article on GitHub about a recommended [development envirnonment](https://github.com/SEP007/resources/blob/master/development-environment.md) are meant to give advice in this regard.

After having setup an environment the application can be installed within its so called document root. For this purpose the repository has to be cloned from [GitHub](https://github.com/SEP007/lmvc-patat). Then possibly system dependend configuration has to be performed copying sample configuration files into their actual, from the version control, ignored equivalents. Lastly, the database dumps from modules and the application have to be imported into the local database. All there steps and their discription are still visible in an old commit of the project's [readme](https://github.com/SEP007/lmvc-patat/blob/860ed4dd5c52644b324f94676d7dfcfa9be4c269/README.md).

## The new state

Due to the fact that the original installation took about seven manual steps it has been decided to automate as many of them as possible. Copying of files, calling dependency managers to fetch projects and cloning the repository can be executed from a command line anyway. This is why common tasks are not automated using shell scripts which can be found under the project's [script-directory](https://github.com/SEP007/lmvc-patat/tree/master/scripts).

The installation of the current version of the application can hereby be accomplished with just one command `bash -c "$(curl -fsSL http://git.io/xzIkXA)"` from the command line when being in Apache's document root. It only tells the shell to fetch a script from that remote url and execute the code within it. Not particularily secure and prone to Dynamic Name Service (DNS) redirects but still an often used way to install applications on UNIX systems these days.

The only manual step is importing the database after running the command and maybe settings some database credentials whenever they differ from the suggested ones. All still mentioned in the updated project's [readme](https://github.com/SEP007/lmvc-patat/blob/master/README.md).

## The improvements

The changes reduced the steps involved in an installation from seven to two to three. Furthermore, they eliminate the need to keep an updated version of installation instructions as everything is bundled in the responsible scripts. The same applies for updating and testing the system for which more scripts have been created.

## The production server

The production server can be easily updated using the same process. Anyhow, it has been decided to have a pull- procedure rather than a push-oriented one. In the first scenario the server is updated by specifically telling him to fetch the latest sources and update dependencies accordingly. The latter would imply the ability of pushing to the productions server whenever needed which was not needed nor advisable in the development process at hand.

## Problems along the way

Interestingly enough this was the first time the whole system was installed on Windows machines for development. As no previous developer was working on a Windows machine and it has some minor but significant differences it causes a whole set of issues. Mostly rooted in different handling of paths and directory persmissions between UNIX and Windows systems. Moreover, a Windows command line does not support standardized shell scripts which forces users to fall back to a manual installation process.

It has been decided to address issues of being unable to run and develop the system from Windows machines. For this bug-tickets were opened and ultimativly closed. Specifically for e.g. the Asset Pipeline [here](https://github.com/SEP007/lmvc-modules/issues/6) and more general for all modules [here](https://github.com/SEP007/lmvc-modules/pull/7).

Anyhow, it has been decided to not automate the installation for Windows users as 80% of developers are using UNIX like systems after all.