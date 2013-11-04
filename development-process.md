# Development Process

## Agile & its Methodologies

### Kanban & Issues

The group will develop in a Scrum fashion using a Kanban board to visualize the flow. Anyhow, sprints are still time-boxed and there is not such a thing as a Work in Progress (WIP). A sprint will start up with a planning meeting on Monday and will finish with an acceptance test on its last day. In between the team will have daily standups on every meeting day to answer the usual questions:

- What are you working on?
- What will you be working on?
- What are current problems?

Our internal development repositories are setup up to use [GitHub Issues](https://github.com/blog/831-issues-2-0-the-next-generation) which integrate kindly into development if you take some time to understand them but they are fairly easy after all.

Moreover, Huboard (one of our project proposals) has been setup to be used with our project. The reason to pick it over the *Pivotaltracker* is solely the fact that it integrates with *GitHub Issues*. Thereby, every issue can be tagged with one of `Backlog`, `Ready`, `Working` or `Done` which will make them show up in the appropriate Kaban board's (Huboard) column. Other tag such as `bug` or `enhancement` can obviously also be assigned. Huboard is thereby just a visual Kanban-board-ish representation of our *GitHub Issue Tracker*.

Stories shall be tagged according to their nature in `User Story`, `Developer Story` and `Restaurant Story`. They will then be attached to a milestone which is a sprint in Agile fashion. A sprint will usually last one week but the first will last two as every team member has to get familiar with the system. This tries to take the learning curve into account and can be adjusted and discussed later on depending on the teams' opinions on it.

Each story will be developed in its own branch which will be related to a pull-request to embrace disucssions upon it. A reviewer will be assigned to every story during the spring planning meeting. The reviewer should be contantly involved in a stories development and be able to comment on relating commits. During the groups' acceptance test on the sprint's last day, the group will discuss all features again and decide if they can me merged into `master`.

Every feature which is non-interface related and testable should be tested to have an >= 60% code-coverage. The coverage details will be visible on each project repository and gathered using TravisCI for continuous integration. Furthermore, each member can inspect files and their degree of coverage whenever running a test-suite.

The overall KanBan for user stories and bugs is available under [Patat' Huboard](http://huboard.com/SEP007/lmvc-patat) and its [issue page](https://github.com/SEP007/lmvc-patat/issues). Open and closed pull-requests are accessible within their dependent repository and will link back to Patat's "global" issue tracker. All to have a central view of bugs and changes. Whenever a issue mentions a pull-request (even in another repository) its gonna show up in the pull-reqeusts history.

The group intends to use some further Agile methodologies during this project. Anyhow, XP has been dropped in favor of just working together and helping out where possible whenver somebody has a question. Continuous Integration and Test-Driven Development on the other hand are endorsed and tried and but their use will be evalutated at a later stage within the project. Furthermore, the group will assign velocities to stories in order to create Burndown Charts. Still, these will not be very valuable within the beginning as everybody has to make himself familiar with the system.

The story points will be assigned during the team's weekly planning session. Numbers assigned should be of the fibonacci sequence between 1-13 and estimate a user stories relative complexity compared to other stories. The team's fixed velocity throughput per sprint should be around 50-60 but can be adjusted in regard to the members' learning curve. The first sprints user stories will be used as an experienced based reference for further estimations which will always build up on the previous estimations.
A weekly planning session will start by the team putting up possible user stories on a whiteboard comparing and estimating them during a discussion. According to the velocities assigned, the team will pick the stories for the next sprint.

## On Commits & Git

Changes to libraries should be made in seperate branches which later can be pulled into the *master* with *pull requests*. This [article](http://nvie.com/git-model/) decribes a sustainable branching model. Stating that every feature, bug, etc should be developed in a single branch as in `feature-name` or `bug-name`. The branch's code itself should be reviewed and afterwards be pulled into *master*.
Development branches and the master can of course be pushed to GitHub at any point in time but every commit should contain a buildable project.

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

So by just branching of the `master-branch` with `git checkout -b feature/my-feature` gives you a branch from which you can later create a pull request on GitHub after you pushed the branch with `git push origin -b feature/my-feature`. Now you can create a pull request in the web interface and give some more details including the todo, description etc. The rest happens automatically, even when merging back into master (after commiting changes to your branch) by `git checkout master && git merge feature/my-feature && git push origin master` GitHub will automatically close your pull request and its discussion thread. Obvisouly you might want to sync and merge in master at some time or the latest before merging when still being on your branch by `git pull origin master` (pull is a `fetch` + `merge`!).

A pull-request should contain information about the story you are working on and check points along the way. So an example story could look like:

```markdown
A short description of what and why you develop this particular feature.

# Checklist (Todo list of things until you each the goal)
[ ] Task 1
[ ] Task 2
[x] Task 3

# Questions
Questions in bullet points towards the reviewer and possibly the whole group.

(Issues and stories it shoud close automagically can be mentioned when the pull-request is on the lmvc-patat repo. As only issues within the same repo can be mentioned.)
Fixes #1
Closes #2
```
