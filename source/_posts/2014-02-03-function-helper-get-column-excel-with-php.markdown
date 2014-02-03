---
layout: post
title: "function helper: get column excel with PHP"
date: 2014-02-03 13:59
comments: true
categories: [programming]
keywords: php, helper, codeigniter, get column excel
tags: [php,codeigniter]
author: Andhi Noerdianto
---
```php
<?php
/*
 * @param integer $col
 * return string
 */
function get_column($col)
{
	$columns = array(
			1=>'A',2=>'B',3=>'C',4=>'D',5=>'E',6=>'F',7=>'G',8=>'H',
			9=>'I',10=>'J',11=>'K',12=>'L',13=>'M',14=>'N',15=>'O',16=>'P',
			17=>'Q',18=>'R',19=>'S',20=>'T',21=>'U',22=>'V',23=>'W',24=>'X',
			25=>'Y',26=>'Z'
	);

	$a = floor($col/26);
	$b = $col%26;
	if(($a < 1) or ($a == 1 and $b == 0)) return $columns[$col];
	if($b == 0) return $columns[$a-1] . 'Z';
	$c = $columns[$a] . $columns[$b];

	return $c;
}

#example
echo get_column(30);
?>
```

Regards<br/>
{cahkaibon}
