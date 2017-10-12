---
title: Homework 1
layout: default
---

## Homework 1: Git, HTML, CSS, BootStrap

This first homework tasked us with developing a small series of webpages that meet a certain criteria using HTML, CSS, and BootStrap. At the same time we were to use git through the command line to commit to a repo regularly. The assignment page is [here](http://www.wou.edu/~morses/classes/cs46x/assignments/HW1.html).

#### Git:

The first steps were to create a local git repo and connect it to a github or bitbucket and/or clone one. I went with github for the time being.

To clone a git repo such as github:
```bash
git clone https://github.com/{username}/{project}.git
```

To initilize a local repo and connect it:
```bash
git init
git remote add https://github.com/{username}/{project}.git
git pull
```

To configure the git user:
```bash
git config --global user.name "Blake Bauer"
git config --global user.email bbauer15@wou.edu
```

Git has several commands:
- **add** *file* stages *file* so it can be commited
- **commit** *-m "commit message"* does a local commit 
- **push** *remote branch* pushs to the remote repo
- **merge** *branch* merges the active branch into *branch*
- **fetch** *remote branch* fetchs from the remote
- **pull** *remote branch* fetchs and merges from the remote

Example:
```bash
git add file.html
git commit -m "Added file.html"
git push origin master

//Other machine
git pull
```
