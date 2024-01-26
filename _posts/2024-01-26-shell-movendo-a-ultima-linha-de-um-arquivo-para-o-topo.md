---
layout: post
title: "[SHELL] movendo a última linha de um arquivo para o topo"
description: ""
category: 
tags: 
  - bash
  - sed
status: published
type: post
published: true
---
{% include JB/setup %}

Mais um post para funcionar de memória e não mais ficar buscando como fazer para mover a última linha de um arquivo para o topo.

{% highlight bash %}
 
 $ sed '1h;1d;$!H;$!d;G' file
 
{% endhighlight %}

Referências: 
* [Use sed to move last line to top](https://www.unix.com/shell-programming-and-scripting/128416-use-sed-move-last-line-top.html)
