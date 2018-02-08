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

## What is a Git Merge
- Git does a three way merge. Takes two snapshots pointed to by the branch tips of the branches that are merging and the common ancestor of the two. Instead of just moving the branch pointer forward, Git creates a new snapshot that results from this three-way merge and automatically creates a new commit that points to it.


### Rebase Don'ts
Do not rebase commits that exist outside your repository. Or do not rebase a public branch.

### Rebase Advantages
- Rebasing makes for a cleaner history. If you examine the log of a rebased branch it looks like a linear history. It appears that all the work happened in series even when it originally happened in parallel.

### Rebase Disadvantages
- Rebasing re-writes the project history by creating brand new commits for each commit in the original branch.

### Merge Advantages
- Merging is a non-destructive operation. The existing branches are not changed in anyway

### Merge Disadvantages
- feature branch will have an extraneous merge commit every time you need to incorporate upstream changes. If the master is very active this can pollute your feature branch's history.

### Rebase VS Merge
Its all about history. If you care about preserving what actually happened you should not rebase. The opposing opionion is if you care about the story of how your project was made than you rebase.

---
# Resources
[https://git-scm.com/book/en/v2/Git-Branching-Rebasing](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)
[https://www.atlassian.com/git/tutorials/merging-vs-rebasing](https://www.atlassian.com/git/tutorials/merging-vs-rebasing)
