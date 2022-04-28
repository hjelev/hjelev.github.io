---
layout: post
title: Set git origin to remember credentials
date: 2022-02-08
categories: linux
---
Set in your .bashrc or .zshrc file:

```
export username="git-hub-token"
```

```
git remote set-url origin https://username:$username@github.com/username/repo-name.git
```