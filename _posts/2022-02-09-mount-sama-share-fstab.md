---
layout: post
title: How to mount Samba share on boot
date: 2022-02-08
categories: linux
---
To mount a samba share when Ubuntu boots you need to add a line to your `/etc/fstab` file.
You'll have to update the path to your samba share, local mount folder and your samba credentials. 

```
//remote/path/to/samba/share /local/mount/folder cifs username=your-user-name-here,password=your-password-here,rw,file_mode=0777,dir_mode=0777       0       0
```

After you update your fstab file you need to mount the newly added record, you can do that with the mount command below

```
mount -a
```
