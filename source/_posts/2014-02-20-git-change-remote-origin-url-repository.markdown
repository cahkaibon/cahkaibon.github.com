---
layout: post
title: "git: change remote (origin) url repository"
date: 2014-02-20 13:07
comments: true
categories: [linux]
keywords: git
tags: [git]
author: Andhi Noerdianto
---
```
# show remote url
$ git remote -v
$ git remote rm origin
$ git remote add origin [new_url_repository]
$ git config master.remote origin
$ git config master.merge refs/heads/master
$ git push
```

Regards<br/>
{cahkaibon}
