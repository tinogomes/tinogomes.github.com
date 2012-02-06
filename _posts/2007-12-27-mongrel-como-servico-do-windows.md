---
layout: post
title: "Mongrel como serviço do Windows"
tags:
- mongrel
- rails
- ruby
- windows
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
---
1. Instalar como serviço do windows

		mongrel_rails service::install -N minha_aplicacao_rails -D "Aqui vai uma descricao" -e production -p 5001 -c c:\caminho\da\minha\aplicacao

1. Remover serviço do windows

		mongrel_rails service::remove -N minha_aplicacao_rails
