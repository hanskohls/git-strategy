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




rebasing
========

Rebasing is all about reducing the risk of merging data. Assume the following tree.

* A feature is started at an early stage of development. 
* It is then stalled and reactivated later
* Significant change has occurred on the master branch in the meantime.
* When merging, the changes of both branches are joined up. 


```
      C---D---E   feature
     /         \
A---B-...--AA---AB master
```

By rebasing you move all changes of the feature to the current head of the master branch. 
You can then test the feature in isolation, where the master branch is breaking your feature you fix it. 
Then you merge your work back into the master branch. 

```
       			 C'--D'--E'   feature
            /         \
A---B-...-AA-----------AB   master
```



