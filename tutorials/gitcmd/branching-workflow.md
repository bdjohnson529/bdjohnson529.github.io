---
title: "Branching workflow"
layout: default
parent: CMD Git
parent_path: /tutorials/gitcmd/
---
This document explains the Git workflow to add a new feature to the master branch. Commands are entered into the CMD.

1. **Using CMD, navigate to the project folder.**

		cd C:\User\Documents\MyPath\

2. **Verify that you are up to date with the master branch.**

		git checkout master
		git pull origin master
		git branch

3. **Create a new feature branch.**

		git checkout -b bdj-mynewfeaturebranch

4. **Make your changes!**

5. **Verify your changes.**
Git diff launches the VIM editor. To exit the editor, press *q*.

		git diff

6. **Add your changes to staging.**
To add all tracked files:

		git add -u

To add a specific file:

		git add MyFile

7. **Verify your changes in staging.**

		git status

8. **Commit your changes.**

		git commit -m "My commit message"

9. **Push your local branch to remote.**

		git push origin HEAD
