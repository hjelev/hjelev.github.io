---
layout: post
title: Ubuntu Customizations CLI
date: 2021-`0-04
categories: Ubuntu
---

# How do I enable 'minimize on click' on Ubuntu dock

Open Terminal and run

`gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize'`

To revert to the default option, simply run

`gsettings reset org.gnome.shell.extensions.dash-to-dock click-action`
