## What is git 

Git is a version control system, used to manage the files. It nothing more than a minimum file system with version control 

## How the git achieves version control 

There are two ways to achieve version control 

1. Log,  Using log to record information change. Less space consumption  but difficult to management. 
2. Snapshot, Copy the file when file changes(similar to the idea of copy on write, it is a lazy load too ), it does not record the information change.   Large space consumption but easy management 


## Git phases

1. Untracked , when a new file is added into the git, it is in untracked status, we can use git add .  to add it into git
2. Unstaged, when the file is modified but not being added, we can use add command to add it into git.
3. Staged,  the fie is added to the git, waiting for to be commited 
4. Commited, it has been commited, where the file is added into git repository. 

### Undo operation between pahses. 

1. Make the commited to uncommited  by using git reset ??? and how ?? and we also should be careful about the git reset command .
   Just How ?? 
2. Make staged unstaged  by using git checkout -- 
3. Make unstaged cancel by using git restore 
4. How to delete untracked file, by using git clean??? 

## Git rebase, merge, and cherry pick 

All the three commands are used to merge into another branch. 

Rebase is the first choice to use when there is little conflict and we use rebase to make the commit history clear. 

When to use cherry pick ?

## Branch 
Why branch ???

Branch is nothing more than a minimum file system with a name, the branch name.

When the file in the branch is modified, it can compare with other branches to get the diff. The diff is really important for the code review. 

So the branch is very important for cooperative development. 


## Some advanced tools 


### git stash 

git stash, saved the current uncommited changes, and allow you to swtich the branch. And you can restore the changes by using git stash apply

### git grep

a search tool, we should make full use of it 

### git clean 

cleann all the modified or staged files. 

### git rebase -i 
Interactively edit the commit history message, or combine the multiple commites into one. 


## Git internals 

### Content-Addressable  file system

The data model in git is using content-addressable file system, which is nothing more than a key-value database. The key is the hash of content, which can be implemented by SHA, while the content is the value. And we can use the key to retrieve the content.  

This file system is only used for the unchanged file, if the file is frequently changed, it is costely to maintain the identification of the content. 

### Three objects 

#### Blob Object 
The blob is nothing more than a content which will be stored by content-addressable file system. 

#### Tree object

Tree is very simialr to linux file system tree, it tracks the direcotry and the blob objects. 

#### Commit object

Commit object references to a only one tree object, and also keeps tracking the commit user, commit message information.

So the commit object is a snapshot of current file system. 

Blob object is the most basic object. And the tree object is the organization of directories and blob objects. 

The commit object is the extension of tree object by recording information of committer.

### HEAD

HEAD is used to record the latest commit object of current branch.  It is useful for checking out a new branch.

### REF

Reference is used to bind the branch name to a commit object, so REF is nothong more than a pointer. We can manage REF based on the REF. 
