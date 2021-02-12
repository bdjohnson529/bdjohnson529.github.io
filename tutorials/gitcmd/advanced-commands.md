---
title: "Advanced Git commands"
layout: default
parent: CMD Git
parent_path: /tutorials/gitcmd/
---

# Advanced Git
This tutorial explains advanced usage of Git.

# Commits
## Add all tracked files
		git add -u

# Branches
1. When you don't like some commits, reset to a previous commit and create a new branch.

## Push an unpublished branch
		git push origin HEAD

## Undoing a local commit
		git reset --hard HASH

## Reset a file to a specific version
		git checkout HASH -- Path/To/File.sql

## Delete local branch
		git branch -D BRANCHNAME

## Rebasing
		git checkout FEATURE
		git rebase master
