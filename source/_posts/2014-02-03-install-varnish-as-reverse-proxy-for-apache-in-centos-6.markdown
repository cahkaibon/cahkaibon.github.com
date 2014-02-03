---
layout: post
title: "install varnish as a reverse proxy for apache in centos 6"
date: 2014-02-03 10:43
comments: true
categories: [linux]
keywords: varnish,reverse proxy
tags: [varnish]
author: Andhi Noerdianto 
---
```
$ su -
$ rpm --nosignature -i http://repo.varnish-cache.org/redhat/varnish-3.0/el6/noarch/varnish-release/varnish-release-3.0-1.el6.noarch.rpm
$ yum -y install varnish
```

case:<br/>

- varnish in port 80
- apache in port 8080

```
$ vi /etc/varnish/default.vcl
change:
	backend default {
		.host = "127.0.0.1";
		.port = "80";
	}
to:
	backend default {
                .host = "127.0.0.1";
                .port = "8080";
        }

$ vi /etc/sysconfig/varnish
change:
	VARNISH_LISTEN_PORT=6081
to: 
	VARNISH_LISTEN_PORT=80

$ vi /etc/httpd/conf/httpd.conf
change:
	LISTEN 80
to:
	LISTEN 8080

$ service httpd restart
$ service varnish start
$ chkconfig varnish on
```
