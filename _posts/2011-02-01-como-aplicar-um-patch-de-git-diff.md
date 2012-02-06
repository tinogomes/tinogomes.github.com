---
layout: post
title: Como aplicar um patch de `git diff`
tags:
- diff
- git
- patch
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1299376587";}
  _edit_last: "2440922"
  jabber_published: "1296595981"
  _wpas_done_twitter: "1"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090340";}
  _wpas_done_yup: "1"
---
Criando o arquivo de patch

	$ git diff &gt; /tmp/arquivo.patch

Aplicando o patch

	$ patch -p1 &lt; /tmp/arquivo.patch

Baseado [no post de Thomas Amsler sobre o assunto](http://tamsler.blogspot.com/2009/02/patching-with-git-diff.html).
