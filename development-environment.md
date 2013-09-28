# The Development Environment

## Introduction

Each member should be able to develop locally to not interfer with changes of anybody else on the live server. The live server is only a representation of a certain stage of development overall and is completely independent from any development.
The live server will subsequently just pull in a certain stage of the development and fetch its dependencies.

## System Requirements

The system requirements for development are as follows

* PHP > 5.4
* Apache 2.0
* MySQL > 5.5

## Local Development Environment

Every team member should set up her/his own AMP-stack using any of the packages out there.

* [Mamp](http://www.mamp.info/) is an option for Mac OS
* [XAMPP](http://www.apachefriends.org/) for Windows and Linux

It's obviously a possibility to setup everything with just a package manager such as *apt-get* or *homebrew*.

After you finished setting up for AMP-stack and defined your htdocs-root, continue reading the [setup intructions](patat-installation.md).

## Recommended IDEs

There're a bunch of IDEs out there and I'd advice anybody to use the one he/she is most confortable/productive in.

Anyhow, this is a list of suggestions in order of my own preference.

* [http://www.jetbrains.com/phpstorm/](PHPStorm)
* [Sublime Text](http://www.sublimetext.com/3) (just an text editor)
* [Eclipse with PDT](http://www.eclipse.org/pdt/downloads/)

## Git Clients

IDEs might integrate with git and GitHub but you can also choose an external tool for interaction with the version control system.

* [SourceTree](http://www.sourcetreeapp.com/) Mac & Windows
* [Tower](http://www.git-tower.com/) Mac only
* [Gitbox](http://gitboxapp.com/) Mac only
* GitHub [Mac](http://mac.github.com/) & [Windows](http://win.github.com/)
* [Git-cola](http://git-cola.github.io) Linux
* [Gitg](https://wiki.gnome.org/Gitg) Linux
* [SmartGitHq](http://www.syntevo.com/smartgithg/)

## Live Server

We have a live, publically available server running at [sep007.tdeekens.name](http://sep007.tdeekens.name).

It's document root has a clone of our *lmvc-patat* GitHub repository. Thereby allowing us to pull directly from our repository. It manages php-dependencies by composer and can update them at any time.
Lastly, the apache is configured to use php 5.5 and any database migration has to be performed manually at this point using the phpmyadmin backend.