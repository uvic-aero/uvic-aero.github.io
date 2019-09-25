# Git Workshop
This workshop's purpose is to get you up to speed with basics of git!

## What is Git?
Git is a distributed version-control system for tracking changes in source code during software development. 
It is designed for coordinating work among programmers, but it can be used to track changes in any set of files. 
Its goals include speed, data integrity, and support for distributed, non-linear workflows 
([Wikipedia Git](https://en.wikipedia.org/wiki/Git))

So basically, if you and I are working on the same code, we can:
* make changes **concurrently**,
* keep track of our changes **over time**, 
* **revert to old versions** of our code, and
* systematically **merge eachother's code** into one coherent version (this usually happens automatically unless merge conflicts occur... More on that later).

This tutorial will cover the basics of git:

1. [Git Configuration](#git-configuration)
1. [Cloning](#cloning)
1. [Branching](#branching)
1. [Committing](#committing)
1. [Pushing](#pushing)
1. [Merge Conflicts]()
1. [Rebase/Merge](#rebase-or-merge)
1. [Git Ignore](#git-ignore)

Github Development Tools
1. Issues
1. Kanban Boards
1. Assignees
1. Commits
1. Pull Requests
 * Peer Review

## Git Configuration
* Repo level git config
* Global leve git config

## Cloning
* `git clone [repository name]`
* HTTP vs SSH

## Branching
* `git checkout [branch_name]`
* `git checkout -b [new_branch_name]`
* `git branch`

## Committing
* `git commit -a -m "[a description of your commit]"`
* Flags?
  * `-a` Tells the command to automatically stage files that have been modified and deleted, but new files you have not told Git about are not affected.
  * `-m <message>` specifies `<message>` as the commit message

## Pushing
* `git push`

## Rebase or Merge
* `check what branch your on`
* `git fetch`
* `git merge origin master`
#### OR
* `git pull origin master`

## Git Ignore
* `.gitignore`
