---
layout: post
title: Useful CLI tools
date: 2021-12-01
categories: ubuntu, cli
---

## FD
https://github.com/sharkdp/fd/

fd is a program to find entries in your filesystem. It is a simple, fast and user-friendly alternative to find. While it does not aim to support all of find's powerful functionality, it provides sensible (opinionated) defaults for a majority of use cases.

```bash
sudo apt install fd-find
```
Note that the binary is called **fdfind** as the binary name fd is already used by another package. It is recommended that after installation, you add a link to fd by executing command ```ln -s $(which fdfind) ~/.local/bin/fd```

##jq

https://github.com/stedolan/jq

jq is like sed for JSON data - you can use it to slice and filter and map and transform structured data with the same ease that sed, awk, grep and friends let you play with text.

```bash
sudo apt install jq
```