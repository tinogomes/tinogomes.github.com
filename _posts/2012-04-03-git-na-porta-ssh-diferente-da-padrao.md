---
layout: post
title: "Git na porta SSH diferente da padrão"
tags:
- git
- git pull
status: publish
published: true
---
{% include JB/setup %}

Digamos que por motivo de segurança, resolveram mudar o número da porta SSH e você não consegue mais fazer um simples `git pull` então, basta adicionar o prefixo do protocolo `ssh://` e então adicionar o número da porta. Considerando que a porta agora é 2222.

	$ git clone ssh://user@git.repo:2222/path/repo.git

Referências:

* <http://www.bramschoenmakers.nl/en/node/720>
