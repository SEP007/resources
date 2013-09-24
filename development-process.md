# Development Process

## Agile & its Methodologies

### Kanban & Issues

Our internal development repositories are setup up to use [GitHub Issues](https://github.com/blog/831-issues-2-0-the-next-generation) which integrate awesome into development if you take some time to understand them but they are fairly easy after all.

Moreover, Huboard (one of our proposals) has been setup to be used with our project. The reason to pick it over the *Pivotaltracker* is solely the fact hat it integrates with *GitHub Issues*. Thereby, every issue can be tagged with one of `Backlog`, `Ready`, `Working` or `Done` which will make them show up in the appropriate Kaban board's (Huboard) column. Other tag such as `bug` or `enhancement` can obviously also be assigned. Huboard is thereby just a visual Kanban-board-ish representation of our *GitHub Issue Tracker*.

**Links to the boards**

- [Patat](http://huboard.com/SEP007/lmvc-patat)
- [lmvc](http://huboard.com/SEP007/lmvc-lmvc)
- [lmvc-modules](http://huboard.com/SEP007/lmvc-modules)
- [lmvc-troba](http://huboard.com/SEP007/lmvc-troba)
- [scandiojs](http://huboard.com/SEP007/scandiojs)

## On Commits & Git

Changes to libraries should be made in seperate branches which later can be pulled into the *master* with *pull requests*. This [article](http://nvie.com/git-model/) decribes a sustainable branching model. Stating that every feature, bug, etc should be developed in a single branch as in `feature-name` or `bug-name`. The branch's code itself should be reviewed and afterwards be pulled into *master*.
Development branches and the master can of course be pushed to GitHub at any point in time.

Commits on the other hand should contain a logical, closed unit of code. A commit message should be in the imparative form, e.g.: `Adds alphabetical sorting to model collections.` or `Fixes bug where application crashed on clicking back button.`.
You can also close issues on GitHub right from a commit message by having a commit message like: `Fixes #20 where not all data was loaded.`. A commit message itself should not have more than 50 characters as it will be cropped. Longer commit messenges can be made as a list (from terminal or an app):

```bash
Adds sorting functionality to model collections.

- Adds basic sort callback to model classes which can be overwritten
- Implements sorting algorithm as bubble sort (I hate myself)
- Calling sort-fn on collection will sort all models in it using callback
- Adds isSorted indicator if collection is dirty/unsorted or has been sorted
```

After all, commits should communicate changes you made to other group members by their message and code diffs.

## Pull & Feature Requests

Developing features in a pull request based fashion has a couple of advantages. For one, it communicates your status by having a simple list of todos with the pull requests description plus the commits which relate to the functionality (e.g. [Tag Browser in Agile Course](https://github.com/opfo/app/pull/39)). All leading having to main goals: isolated (branch-based) development and async. team-communication. All of which should easily integrate with Huboard too.

So by just branching of the `master-branch` with `git checkout -b feature/my-feature` gives you a branch from which you can later create a pull request on GitHub after you pushed the branch with `git push origin -b feature/my-feature`. Now you can create a pull request in the web interface and give some more details including the todo, description etc. The rest happends automagially, even when merging back into master (after commiting changes to your branch) by `git checkout master && git merge feature/my-feature && git push origin master` GitHub will automatically close your pull request and its discussion thread. Obvisouly you might want to sync and merge in master at some time or the latest before merging when still being on your branch by `git pull origin master` (pull is a `fetch` + `merge`!).