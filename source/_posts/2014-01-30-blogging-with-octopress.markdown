---
layout: post
title: "blogging with octopress"
date: 2014-01-30 09:56
comments: true
categories: [other]
keywords: octopress
tags: [octopress]
author: Andhi Noerdianto
---
**How To 'ngeblog'**
```
$ su blog
$ cd /home/blog/octopress/
$ /bin/bash --login
$ rake new_post["sample"]
$ vi source/_post/yyyy-mm-dd-sample.markdown
$ rake generate
$ rake watch
$ rake preview
$ rake deploy <--- deploy ke github
$ git add .
$ git commit -m 'your message' .
$ git push origin source
```

>**Caution!!!**<br/>
Only for my machine.


Salam<br />cahkaibon
