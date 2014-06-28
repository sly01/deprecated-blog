---
layout: post
title: "Gpg Key Fixing"
date: 2014-06-28 10:46:07 +0300
comments: true
categories: 
---
```
gpg --keyserver pgpkeys.mit.edu --recv-key  PUBKEY
```
```
gpg -a --export PUBKEY | sudo apt-key add -
```
