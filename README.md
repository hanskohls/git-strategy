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

deleting a branch
=================

Sometimes a branch is not required anymore and needs to be deleted. To achive this run

```
git branch -d <branch name>
```


merging
=======

Once the last commit on a branch has been completed you can merge this branch back to the parent branch.
When pushing the merged branch to the remote repository we usually want to retain it. The best approach to do this is to

* push all branches if there is no current branch that you do not want to push
* push the current branch and the specific branch separately.

```
git checkout <parent branch name>
git merge <branch name>
// Finally to push this work to the remote repostiory run
// We usually want to retain the feature branches, to push these out the option --all is required.
git push --all
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

Rebasing is done using the following commands.

```
git rebase master feature
// This may result in some conflicts that need to be resolved. 
// Resolve them and add the amended files. 
// then if requried run
git rebase --continue
```



