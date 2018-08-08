---	
layout: article	
title: git - some useful commands
categories: articles	
excerpt: 
share: true	
---

I've always wanted to collect some useful git commands that I sometime use
during my daily activity. Here are some that, from time to time, I go back to.

* Find the commit that added a line/a block in a file (warning: the line as of
today):

`git log -L start_line,finish_line:filename --format=%an | head -n 1`

* Show old version of a file, given its commit hash (SHA):

`git show <version>:<filename>`

* Show number of lines modified per each developer in a file:

`git blame --line-porcelain <filename> | sed -n 's/^author //p' | sort | uniq -c
| sort -rn`

* Follow a file in git, if it was moved from another folder:

`git log --follow -p <filename>` 
`-p` can be removed as it shows also the diff  

* Full history of a file, even if it has been deleted:

`git log --full-history -- <filename>`

In case the path has been changed, `git log --diff-filter=D --summary | grep <filename>`

