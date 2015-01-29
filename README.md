git-strategy
============

This is a combined git tutorial for my own and other git new-user requirements as well as a branching strategy document.


branching
=========

To create a branch run the following command: 

```
git branch <branchname>
git checkout <branchname>
// Make your changes
git commit -a -m "<commit message>"
// After committing make some more changes and commit again.
```

merging
=======

Once the last commit on a branch has been completed you can merge this branch back to the parent branch.

```
git checkout <parent branch name>
git merge <branch name>
// If you want to delete the subbranch you can run
git branch -d <branch name>
// Finally to push this work to the remote repostiory run
git push
```
