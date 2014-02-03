---
layout: post
title: "variable on the fly in PHP"
date: 2014-02-03 13:26
comments: true
categories: [programming]
keywords: php, variable on the fly
tags: [php]
author: Andhi Noerdianto 
---
creating variable on the fly with PHP:
``` php
<?php
$str = 'testing';
$$str = 'on the fly';
echo $testing;
?>
```
