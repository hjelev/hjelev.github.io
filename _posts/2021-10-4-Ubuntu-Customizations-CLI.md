---
layout: post
title: Ubuntu Customizations CLI
date: 2021-10-04
categories: ubuntu
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

# Create wallpaper slideshow using a bash script and cron
Save this script as a bash file and schedule it with a cronjob
```
#!/usr/bin/env bash
# Get the Real Username
RUID=$(who | awk 'FNR == 1 {print $1}')

# Translate Real Username to Real User ID
RUSER_UID=$(id -u ${RUID})

DIR="/home/masoko/Pictures/wallpapers/reddit"
PIC=$(ls $DIR/* | shuf -n1)

# Set gsettings for the Real User
sudo -u ${RUID} DBUS_SESSION_BUS_ADDRESS="unix:path=/run/user/${RUSER_UID}/bus" gsettings set org.gnome.desktop.background picture-uri "file://$PIC"

# /usr/bin/gsettings set org.gnome.desktop.background picture-uri "file://$PIC"
exit
```
