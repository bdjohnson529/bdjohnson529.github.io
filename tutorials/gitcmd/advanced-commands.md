---
title: "Advanced Git commands"
layout: default
parent: Git CLI
parent_path: /tutorials/gitcmd/
---
This tutorial explains advanced usage of Git.


## Undoing a local commit
```bash
git reset --hard HASH
```

## Reset a file to a specific version
```bash
git checkout HASH -- Path/To/File
```

## Delete local branch
```bash
git branch -D BRANCHNAME
```

## Rebasing
```bash
git checkout FEATURE
git rebase master
```

## Remove untracked local files
```bash
git clean -n
git clean -f
```