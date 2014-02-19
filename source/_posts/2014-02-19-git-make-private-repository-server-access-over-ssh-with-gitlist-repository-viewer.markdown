---
layout: post
title: "git: make private repository server access over ssh with gitlist repository viewer"
date: 2014-02-19 16:27
comments: true
categories: [linux]
keywords: git
tags: [git]
author: Andhi Noerdianto 
---
Requirements:

- Apache
- PHP
- Git
- Gitlist

Sample environment:

- Path repositories: /opt/repositories
- Path apache document root: /var/www/html
- Path to git executable: /usr/bin/git
- Apache root url: http://localhost

<!-- more -->

```
# create user access ssh
$ useradd git
$ passwd git

# create path repositories
$ mkdir -p /opt/repositories
$ chown git:git /opt/repositories

# download gitlist
$ wget -c https://s3.amazonaws.com/gitlist/gitlist-0.4.0.tar.gz
$ tar -xzvf gitlist-0.4.0.tar.gz
$ mv gitlist /var/www/html/gitlist
$ restorecon -r /var/www/html/gitlist
```

setup gitlist:
```
$ cd /var/www/html/gitlist
$ mv config.ini-example config.ini
$ mkdir cache
$ chmod 777 cache
$ vi config.ini

# change according your environment
client = '/usr/bin/git' ; Your git executable path
default_branch = 'master' ; Default branch when HEAD is detached
repositories[] = '/opt/repositories/'
```

create repository:
```
$ su git
$ cd /opt/repositories
$ mkdir testing.git
$ cd testing.git
$ git --bare init
$ exit
```

testing access git from client:
```
$ git clone ssh://git@your-server-ip-or-domain/opt/repositories/testing.git
$ touch readme
$ git add .
$ git commit -m 'first commit' .
$ git push origin master
```

testing access from your browser for view list repositories: http://localhost/gitlist

