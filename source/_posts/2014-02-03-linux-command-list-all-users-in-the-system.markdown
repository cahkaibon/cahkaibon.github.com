---
layout: post
title: "linux command: list all users in the system"
date: 2014-02-03 16:20
comments: true
categories: [linux]
keywords: linux, list all users
tags: [linux, command]
author: Andhi Noerdianto 
---
```
$ cat /etc/passwd

to list only username type the following awk command:
$ awk -F':' '{ print $1}' /etc/passwd
```

Regards<br/>
{cahkaibon}

