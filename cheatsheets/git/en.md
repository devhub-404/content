---
locale: en
status: published
title: "Git"
slug: git
description: "A task-oriented Git quick reference for everyday changes, branches, remotes, history, undoing, recovery, and maintenance."
tags:
  - git
  - version-control
  - cheatsheet
references:
  - label: "Git Reference"
    url: https://git-scm.com/docs
  - label: "Pro Git"
    url: https://git-scm.com/book/en/v2
  - label: "Git Glossary"
    url: https://git-scm.com/docs/gitglossary
---

# Git

Task-oriented quick reference for everyday Git. Start with `git status` when you are unsure what state the repository is in.

## Setup & Repository

**Check the Git version**

```bash
git --version
```

**Set your name and email**

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

**See configuration and where it comes from**

```bash
git config --list --show-origin
```

**Create a repository**

```bash
git init
```

**Clone a repository**

```bash
git clone <repository-url>
```

**Clone into a named directory**

```bash
git clone <repository-url> my-project
```

**Get help for a command**

```bash
git help commit
# or
git commit --help
```

## Status & Changes

**See the current state**

```bash
git status
```

**Use compact status**

```bash
git status --short
```

**See unstaged changes**

```bash
git diff
```

**See staged changes**

```bash
git diff --staged
```

**See changes in one file**

```bash
git diff -- src/app.js
```

**See changed filenames only**

```bash
git diff --name-only
```

**See a change summary**

```bash
git diff --stat
```

## Staging & Commits

**Stage one file**

```bash
git add src/app.js
```

**Stage everything under the current directory**

```bash
git add .
```

**Stage tracked-file changes only**

```bash
git add -u
```

Does not add new untracked files.

**Stage selected hunks**

```bash
git add -p
```

**Unstage one file and keep its edits**

```bash
git restore --staged src/app.js
```

**Commit staged changes**

```bash
git commit -m "Add authentication"
```

**Commit tracked-file changes directly**

```bash
git commit -am "Fix validation"
```

Does not include new untracked files.

**Change the last commit message**

```bash
git commit --amend
```

**Add forgotten changes to the last commit**

```bash
git add forgotten-file.js
git commit --amend --no-edit
```

Avoid amending commits that collaborators already use unless rewriting shared history is intentional.

## Branches

**List local branches**

```bash
git branch
```

**List local and remote branches**

```bash
git branch -a
```

**Create and switch to a branch**

```bash
git switch -c feature/login
```

**Switch branches**

```bash
git switch main
```

**Switch to the previous branch**

```bash
git switch -
```

**Rename the current branch**

```bash
git branch -m new-name
```

**Delete a merged branch**

```bash
git branch -d feature/login
```

**Force-delete a local branch**

```bash
git branch -D feature/login
```

Commits reachable only from that branch may become difficult to find.

**See merged branches**

```bash
git branch --merged
```

**See branches containing a commit**

```bash
git branch --contains <commit>
```

## Remotes & Sync

**List remotes**

```bash
git remote -v
```

**Add a remote**

```bash
git remote add origin <repository-url>
```

**Change a remote URL**

```bash
git remote set-url origin <repository-url>
```

**Fetch remote changes**

```bash
git fetch origin
```

Fetch updates remote-tracking refs without changing your current branch.

**Fetch and prune stale remote branches**

```bash
git fetch --prune
```

**Pull with fast-forward only**

```bash
git pull --ff-only
```

**Pull using rebase**

```bash
git pull --rebase
```

**Push the current branch**

```bash
git push
```

**Push a new branch and set upstream**

```bash
git push -u origin feature/login
```

**Delete a remote branch**

```bash
git push origin --delete feature/login
```

**Force-push with a lease**

```bash
git push --force-with-lease
```

Safer than blind --force because it checks the remote ref is still the value you expected.

## History & Search

**Show commit history**

```bash
git log
```

**Use compact history**

```bash
git log --oneline
```

**Show a graph of all refs**

```bash
git log --oneline --graph --decorate --all
```

**Show one commit**

```bash
git show <commit>
```

**Show history of one path**

```bash
git log -- path/to/file
```

**See who last changed each line**

```bash
git blame path/to/file
```

**Search tracked files**

```bash
git grep "search text"
```

**Find commits that added or removed a string**

```bash
git log -S "search text"
```

**Search commit messages**

```bash
git log --grep="authentication"
```

## Undo & Recovery

**Discard unstaged changes in one file**

```bash
git restore src/app.js
```

Uncommitted changes in that file are lost.

**Discard all unstaged changes**

```bash
git restore .
```

**Restore a file from another commit**

```bash
git restore --source=<commit> path/to/file
```

**Undo the last commit and keep changes staged**

```bash
git reset --soft HEAD~1
```

**Undo the last commit and keep changes unstaged**

```bash
git reset HEAD~1
```

**Discard the last commit and its changes**

```bash
git reset --hard HEAD~1
```

Danger: --hard can destroy uncommitted changes.

**Safely undo a published commit**

```bash
git revert <commit>
```

Creates a new commit instead of rewriting existing history.

**Recover after a bad reset or rebase**

```bash
git reflog
git switch -c recovered-work <commit>
```

**Save commits made in detached HEAD**

```bash
git switch -c experiment
```

## Stash

**Temporarily save tracked changes**

```bash
git stash push -m "work in progress"
```

**Include untracked files**

```bash
git stash push -u -m "work in progress"
```

**List stashes**

```bash
git stash list
```

**Inspect one stash**

```bash
git stash show -p stash@{0}
```

**Apply a stash without deleting it**

```bash
git stash apply stash@{0}
```

**Apply and remove the latest stash**

```bash
git stash pop
```

**Delete one stash**

```bash
git stash drop stash@{0}
```

## Merge, Rebase & Cherry-pick

**Merge a branch into the current branch**

```bash
git merge feature/login
```

**Abort an in-progress merge**

```bash
git merge --abort
```

**Rebase the current branch onto main**

```bash
git rebase main
```

**Interactively rewrite recent commits**

```bash
git rebase -i HEAD~5
```

**Continue after resolving rebase conflicts**

```bash
git add <resolved-files>
git rebase --continue
```

**Abort an in-progress rebase**

```bash
git rebase --abort
```

**Apply one existing commit here**

```bash
git cherry-pick <commit>
```

**Abort an in-progress cherry-pick**

```bash
git cherry-pick --abort
```

## Tags, Worktrees & Submodules

**List tags**

```bash
git tag
```

**Create an annotated tag**

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
```

**Push one tag**

```bash
git push origin v1.0.0
```

**Push all tags**

```bash
git push --tags
```

**Create another working tree**

```bash
git worktree add ../hotfix hotfix
```

**List working trees**

```bash
git worktree list
```

**Clone including submodules**

```bash
git clone --recurse-submodules <repository-url>
```

**Initialize and update submodules**

```bash
git submodule update --init --recursive
```

## Diagnosis & Cleanup

**Find the commit that introduced a regression**

```bash
git bisect start
git bisect bad
git bisect good <known-good-commit>
# test, then mark each candidate good or bad
git bisect reset
```

**Preview untracked files that clean would delete**

```bash
git clean -n
```

**Delete untracked files**

```bash
git clean -f
```

Files that were never committed may be unrecoverable.

**Preview untracked files and directories**

```bash
git clean -nd
```

**Check repository object integrity**

```bash
git fsck --full
```

**Run repository maintenance**

```bash
git maintenance run
# or, when appropriate
git gc
```
