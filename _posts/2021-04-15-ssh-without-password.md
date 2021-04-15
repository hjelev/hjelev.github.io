---
layout: post
title: How to ssh using a certificate (not password)
date: 2021-04-15
categories: raspberry-pi
---

1. Generate the certificate on the machine you are going to login from:
```
ssh-keygen
```
2. Check the certificate to make sure it was generated properly:
```
cat ~/.ssh/id_rsa.pub
```
3. Copy the certificate to the remote machine:
```
ssh-copy-id user@host
```
When you execute ssh-copy-id you'll be asked for the password of the remote host.
