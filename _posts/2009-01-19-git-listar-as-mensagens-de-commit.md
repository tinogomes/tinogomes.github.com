---
layout: post
title: "Git: listar as mensagens de commit"
tags:
- changelog
- git
- git-log
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1297205817";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1314205635";}
---
Uma forma interessante de gerar um changelog, usando as mensagens de commit do git:

	$ git log my_tag..HEAD --pretty=oneline

Como resultado, teremos:

	e3478d36697e7285fca91ab4a731debcb8aea110 - Post CRUD
	1b3b753ba397fed1e9223c108b6a267c43b00dcc - Comment CRUD
	99f480667cb95c2a394f06daf2bf23b2fa0ce0b9 - User CRUD
