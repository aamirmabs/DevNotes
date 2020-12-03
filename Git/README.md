# Git DevRef

## Branching

### The What?

Branching in Git allows you to keep your working code (`master branch`) separate from your `development branch` where things could break with changing code. Git allows branches to exist independent of other branches.

### The Why?

Let us try to visualize why we would use branching and merging:

- You have an app in production(`master branch`) and you want to add new features.
- You create a branch `feature abc` from the `master` and start tweaking around the code.
- There is some issue which needs to be fixed immediately. So you pause what you are doing on the `feature abc` branch.
- Switch to `master`, then make another branch for the hot fix `hotfix for xyz issue` and start working on fixing the issue.
- You fix the issue and `merge` the changes from `hotfix for xyz issue` to `master`. The `master` branch now contains all the original code plus the code to fix the issue.
- Now you go back to the `feature abc` branch to complete your new feature.
- When you are done, you merge `feature abc` into `master`. At this point you will have working code that has the changes introduced by the hotfix as well as the code for the new feature.

### The How?

#### Branch Creation

The command to create a branch is:

`git branch branch_name` to create a new branch.

`git checkout branch_name` to change from `master` to `branch_name`.

You can perform both the actions with a single command:

`git checkout -b branch_name`

#### Branch Merging

Ideally we will stage all our files with a `git add .` before committing and then subsequently commit with a `git commit -m "commit message here"`.

We can use a single command to add and commit the files with `git commit -a -m "commit message here"`. The `-a` flag is used to automatically add any untracked/changed file to the commit.

Before we merge our branches we should make sure that we have committed all the changes in the branch. Merging two branches happens between the commits. Any unsaved changes (not committed) on either of the branches will be lost.

Things to keep in mind before merging:

- Save all changes and commit them
- Change to the branch you want to commit to before committing. If you want to merge your `feature xyz` branch to `master` branch, you need the be on the `master` when you initiate the merge.

The command to merge **`branch2` into `branch1`** you will:

- First be on `branch1`: `git checkout branch1`
- Then merge them: `git merge branch2`
