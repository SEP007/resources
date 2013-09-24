# Development Process

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