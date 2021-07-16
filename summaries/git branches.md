# Git Branches

- Source: <https://youtu.be/e2IbNHi4uCI>

## Core Concepts

- The "HEAD" branch: The current branch that you are using
- Local x Remote branches: We work on Local branches, remote branches is for syncronazing

## Comands

### Create new branch
- From the last commit: ```git branch <my-new-branch>```
- From any othercommit ```git branch <my-new-branch> <commit-hashcode>```
- Obs: We create only LOCAL branches

### Switching Branches
- ``git switch <other-branch>````
- ```git checkout <other-branch>``` (this comand does another things too, so it is better use switch)

### See all branches
- ```git branch```: It will appear a list of all branches names, and in a different collor the main branch
- ```git branch -v```: Same thing, but with aditional information

### Renaming Branches
- Local branch:
  - HEAD branch: ```git branch -m <new-name>```
  - Other branch: ```git branch -m <older-name> <new-name>```
- Remote Branch: (steps)
  1. ```git push origin --delete <old-name>```
  2. ```git push -u origin <new-name>``` (the same branch in Local machine already renamed)

### Publishing Branches
- ```git push -u origin <local-branch>``` (This is the way that we "create" remote branches, it is actualy a "uploading" of a local branch)

### Tranking Branches
- ```git branch --track <my-local-branch> <remote-branch>``` (Created a new local brach based on a remote branch
- ```git checkout --track <remote-branch>``` (Create a local branch with the same name of the remote branch)

### Pulling + Pushing Branches
- ```git pull``` and ```git push``` (If we do the traking thing this is all we need)

### Delete Branches
- Local
  - ```git branch -d <branch-to-delete>```
  - Obs: We cannot delete the HEAD branch
- Remote
  - ```git push origin --delete <branch-to-delete>```   

