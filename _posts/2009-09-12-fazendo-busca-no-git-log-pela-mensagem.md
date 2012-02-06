---
layout: post
title: Fazendo busca no git log pela mensagem
tags:
- git
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1298691187";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1324475324";}
---
As vezes queremos fazer uma busca no log do git por algum termo que esta na mensagem, então para isso...

	$ git log --grep=like --regexp-ignore-case --no-merges --pretty=oneline
	ff87a6f5 Added new like tests
	703c791 Added a LIKE test using fields
	dee06dd Mongodb Conditions Compiler: LIKE operator; test if the node is a field
	30aca6a Mongodb: optimization on LIKE operator
	98df7a0 Implemented the LIKE operator

O que fizemos foi fazer a busca pelo termo like, ignorando case sensitive (LIKE, lIkE, like, etc...), ignorando os commits de merge e listando tudo em uma linha simples.
