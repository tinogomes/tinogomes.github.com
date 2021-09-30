---
layout: post
title: git bisect
tags:
- git
- git-bisect
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090364";}
  _wpas_skip_yup: "1"
  _wpas_skip_twitter: "1"
  _wpas_skip_fb: "1"
---
Preparando um material para falar sobre git, algumas técnicas e outras dicas, dentre elas resolvi demostrar o uso do [git bisect](http://www.kernel.org/pub/software/scm/git/docs/git-bisect.html), e usei como base o [post do Arthur Geek](http://www.arthurgeek.net/git-bisect/). Então, resolvi fazer [uma aplicação nada trivial (um blog)](http://github.com/tinogomes/my_blog_app_with_bug) e em um certo ponto dos commits, forcei um erro para usar o git bisect e encontra-lo. Aproveitei para dar uma lida na documentação para pegar mais algum detalhe e me deparei com a opção "run" que automatiza a busca pelo commit ruim, usando um script ou comando que avalia o ponto de parada. Como na minha aplicação exemplo estava coberta por testes e o erro forçado era capturado, logo ficou muito mais legal. Abaixo segue resumido os passos seguidos, mas [todo o console](http://gist.github.com/144170) você dá uma olhada no meu gist.

1. Listando o log de commits para identificar um ponto bom e outro ruim.

		$ git log

1. Após identificados os commits, iniciando o git bisect

		$ git bisect start HEAD a17411e98d7b5

1. Deixando o git bisect buscar o ponto de inicio da falha, com rake test:units

		$ git bisect run rake test:units

1. Identificado o ponto de erro, então vamos para o git bisect

		$ git bisect reset

1. Vamos listar o diff entre os commits com erro e anterior

		$ git diff <strong>7d91b350196ccc 0765b113edefb9</strong>

**as chaves de commit acima foram abreviadas para facilitar, mas está completo no log**
