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

# How to make dock background 80% transparent in Ubuntu

First enable custom colors:

`gsettings set org.gnome.shell.extensions.dash-to-dock transparency-mode 'FIXED'`

Then, to set transparency to 80%, issue the command

`gsettings set org.gnome.shell.extensions.dash-to-dock background-opacity 0.2`

Change 0.0 to any number between 0 and 1.

To reset to the default setting:

`gsettings reset org.gnome.shell.extensions.dash-to-dock background-opacity`
