---
layout: post
title: Rename bluetooth device in Ubuntu
date: 2022-10-18
categories: linux
---

Use bt-device (part of the bluez-tools package).
```
sudo apt install bt-device
```
Get a list of paired devices:
```
bt-device -l
```
To set the new alias:
```
bt-device --set macaddress|name Alias "New Name"
```
ie:
```
bt-device --set S530 Alias "S530 Blue"
```