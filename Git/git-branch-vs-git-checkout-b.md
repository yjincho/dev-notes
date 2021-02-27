# Git branch vs git checkout -b

When creating a new branch, you can use `git branch` but also `git checkout -b`, the difference is as follows:

## Git branch:
Creating a new branch but leaves you on the same branch.
```
$ git branch <branch_name>
```

## Git checkout -b:
Creating a new branch and checks out the new branch.
```
$ git checkout -b <branch_name> 
```