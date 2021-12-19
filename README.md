# GIT FLOW

Have for objective improving the branches uses


- Start project 

```git
git init
git flow init
```


## Branches

Branches in git is a simply pointer to a commit. 

![](https://wac-cdn.atlassian.com/dam/jcr:cc0b526e-adb7-4d45-874e-9bcea9898b4a/04%20Hotfix%20branches.svg?cdnVersion=137)


### Main Branch (Master)

In this branch, we have the production code. 

The develop branch and master branch are the only permanent branches. All others are excluded after use. 

### feature

In these branches, we should be created new features. This type of branch should always be cloned from the development branch, and after finished, the new features should be merged back to the development branch. 

New features are created with the default name "feature / new feature".

- Create new feature

```git
git flow feature start newFeature
```

After finishing your new features, we have to merge this branch to the develop branch. After running this command, this branch is automatically removed from git. 


```git
git flow feature finish newFeature
```

### Develop 

The developers will clone this branch to create new features. In the next steps, after a group of new features, the developers will merge this branch with the release branch are identifying by tags.


### Release

Here we have one branch between the master branch and the developed branch. This branch is responsible to protect the master branch, and It can show a preview of the system to clients/customers, before the implementation. 

```git
git flow release start tagName
```

After finish, the master branch and develop branch are updated.

```git
git flow release finish tagName
``` 


code review
esc :wq!

rotular o commit e tag. 


### Hotfix

In this branch, we have the solution to critical problems in the master branch. That's why, this branch is merged and cloned with the master.

```git
git flow hotfix start hotfix_branch
git flow hotfix finish hotfix_branch
``` 


### Bugfix

In this branch, we have the solution to critical problems in the develop branch. That's why, this branch is merged with the develop branch. It's the responsibility of the QA team.


## Summary

The overall flow of Gitflow is:

1. A develop branch is created from main
2. A release branch is created from develop
3. Feature branches are created from develop
4. When a feature is complete it is merged into the develop branch
5. When the release branch is done it is merged into develop and main
6. If an issue in main is detected a hotfix branch is created from main
7. Once the hotfix is complete it is merged to both develop and main


