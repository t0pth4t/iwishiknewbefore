---
title: Git Merge vs Rebase
date: 2018-02-07 19:19:40
tags: dev
---

## What is a Git Rebase
- It solves the same problems as git merge. Designed to integrate changes from one branch to another.
- Takes all of the changes that were committed on one branch and replays them on another one.
- Rebasing replays changes from one line of work onto another in the order they were introduced whereas merging takes the endpoints and merges them together.
- When you rebase stuff you're abandoning existing commits and creating new ones that are similar but different.
- Rebasing moves the entire feature branch to begin on the tip of the master branch.
- Git rebasing is like saying "I meant to start here"
- Plucks commits from a branch one by one chronologically and reattaches them to a different commit

## What is a Git Merge
- Git does a three way merge. Takes two snapshots pointed to by the branch tips of the branches that are merging and the common ancestor of the two. Instead of just moving the branch pointer forward, Git creates a new snapshot that results from this three-way merge and automatically creates a new commit that points to it. A merge commit represents every change that has occurred on a feature branch since it branched from master.


### Rebase Don'ts
Do not rebase commits that exist outside your repository. Or do not rebase a public branch. Never rebase on a public branch. Think about what would happen if you rebased master onto your feature branch. The rebase moves all of the commits in master onto the tip of the feature. The problem is that this only happened in your repository All of the other developers are still working with the original master. Since rebasing results in brand new commits git will think that your master branch's history has diverged from everybody else's.

Before you rebase always think to yourself is anyone else looking that this branch

### Rebase Advantages
- Rebasing makes for a cleaner history. If you examine the log of a rebased branch it looks like a linear history. It appears that all the work happened in series even when it originally happened in parallel.
- Results in a perfectly linear project history
- Interactive rebasing allows you to clean up a messy history before merging a feature branch into master
- Rebasing does not create an extra commit. If all we're doing is keeping our feature branch up to date with master this is arguably not a meaningful commit

### Rebase Disadvantages
- Rebasing re-writes the project history by creating brand new commits for each commit in the original branch.

### Merge Advantages
- Merging is a non-destructive operation. The existing branches are not changed in anyway

### Merge Disadvantages
- feature branch will have an extraneous merge commit every time you need to incorporate upstream changes. If the master is very active this can pollute your feature branch's history.
- Merge commits can clutter up your git logs and make it much more difficult to understand the flow of your project's history

### Rebase VS Merge
Its all about history. If you care about preserving what actually happened you should not rebase. The opposing opinion is if you care about the story of how your project was made than you rebase. Overall rebasing feature branches from the active develop branch seems to be the right idea.

---
# Resources
[https://git-scm.com/book/en/v2/Git-Branching-Rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
[https://www.atlassian.com/git/tutorials/merging-vs-rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
