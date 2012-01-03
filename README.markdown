Github Workflow
===============

Start a new feature
-------------------

    git branch --track feature_name origin/master

`--track` tells git to setup a remotely tracked branch

Branching from `origin/master` means we don't have to remember to update our
local copy of the master branch to ensure we are working on the latest code.

Starting a pull request for feature discussion and review
---------------------------------------------------------

1. With at least one commit in the feature, go to github and start pull request
   from feature_name to master.

Merging a pull request
----------------------

### Automatic

If the pull request can be automatically merged, click the big green button on
github.

### Manual

github to merge the feature to master.

If the pull request cannot be automatically merged:

**Step 1**: Bring in the changes and test

    git fetch origin
    git checkout -b feature_name origin/feature_name

**Step 2**: Make sure the feature branch is up to date.

    git merge master

**Step 3**: Merge the changes and update the server

    git checkout master
    git merge feature_name
    git push origin master
