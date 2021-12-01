---
layout: post
title: Useful CLI tools
date: 2021-12-01
categories: ubuntu, cli
---
# Github repos for some usefull CLI tools I use daily
## fd
[https://github.com/sharkdp/fd/](https://github.com/sharkdp/fd/){:target="_blank"}

fd is a program to find entries in your filesystem. It is a simple, fast and user-friendly alternative to find. While it does not aim to support all of find's powerful functionality, it provides sensible (opinionated) defaults for a majority of use cases.

```bash
sudo apt install fd-find
```
Note that the binary is called **fdfind** as the binary name fd is already used by another package. It is recommended that after installation, you add a link to fd by executing command ```ln -s $(which fdfind) ~/.local/bin/fd```
***
## jq
[https://github.com/stedolan/jq](https://github.com/stedolan/jq){:target="_blank"}

jq is like sed for JSON data - you can use it to slice and filter and map and transform structured data with the same ease that sed, awk, grep and friends let you play with text.

```bash
sudo apt install jq
```
***    
## bat
[https://github.com/sharkdp/bat](https://github.com/sharkdp/bat){:target="_blank"}
![bat screenshot](/static/img/bat-screenshot.png)  
bat supports syntax highlighting for a large number of programming and markup languages.  

bat communicates with git to show modifications with respect to the index (see left side bar):

```bash
sudo apt install bat
```
Important: If you install bat this way, please note that the executable may be installed as **batcat** instead of bat (due to a name clash with another package). You can set up a bat -> batcat symlink or alias to prevent any issues that may come up because of this and to be consistent with other distributions:
```bash
mkdir -p ~/.local/bin
ln -s /usr/bin/batcat ~/.local/bin/bat
```
***
## fff
[https://github.com/dylanaraps/fff](https://github.com/dylanaraps/fff){:target="_blank"}

A simple file manager written in bash.
```bash
git clone https://github.com/dylanaraps/fff
cd fff
make install
```
CD on Exit:  
To enable CD on Exit in Bash or Zsh, add this to your .bashrc, .zshrc or equivalent.  
Run 'fff' with 'f' or whatever you decide to name the function.
```bash
f() {
fff "$@"
cd "$(cat "${XDG_CACHE_HOME:=${HOME}/.cache}/fff/.fff_d")"
}
```
***
## duf
[https://github.com/muesli/duf](https://github.com/muesli/duf){:target="_blank"}

Disk Usage/Free Utility (Linux, BSD, macOS & Windows)

```bash
sudo apt install duf
```
***
## exa
[https://github.com/ogham/exa](https://github.com/ogham/exa){:target="_blank"}

exa is a modern replacement for the venerable file-listing command-line program ls that ships with Unix and Linux operating systems, giving it more features and better defaults. It uses colours to distinguish file types and metadata. It knows about symlinks, extended attributes, and Git. And it’s small, fast, and just one single binary.

By deliberately making some decisions differently, exa attempts to be a more featureful, more user-friendly version of ls.

```bash
sudo apt install bat
```
***
## ohmyzsh
[https://github.com/ohmyzsh/ohmyzsh/](https://github.com/ohmyzsh/ohmyzsh/){:target="_blank"}

Oh My Zsh is an open source, community-driven framework for managing your zsh configuration.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Before using ohmyzsh you need to make sure that zsh is installed:  
[zsh installation instructions](https://github.com/ohmyzsh/ohmyzsh/wiki/Installing-ZSH){:target="_blank"}
```bash
sudo apt install zsh
```
Plugins for ohmyzsh:

```
plugins=(git macos common-aliases dirhistory zsh-autosuggestions zsh-syntax-highlighting)
```

All of these plugins come with ohmyzsh and they only need to be included in ``` ~/.zshrc``` except **zsh-syntax-highlighting**, which needs to be installed additionally with the command below:
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

```

ohmyzsh themes I use:  
```
ZSH_THEME="gallois"  
ZSH_THEME="af-magic"  
```