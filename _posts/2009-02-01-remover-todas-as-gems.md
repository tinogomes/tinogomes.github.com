---
layout: post
title: Remover todas as gems
tags:
- ruby
- ruby gems rubygems
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1296261163";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090427";}
---
Todos os créditos para [Rafael Lima](http://rafael.adm.br/), pois ele quem [escreveu o post](http://rafael.adm.br/p/removendo-todas-as-gems-de-uma-so-vez/) e eu só copiei na cara dura mesmo.

	$ sudo gem uninstall –a -x –ignore-dependencies .+
