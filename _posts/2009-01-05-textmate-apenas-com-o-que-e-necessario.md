---
layout: post
title: "Textmate apenas com o que é necessário"
tags:
- agil
- alias
- bash
- geral
- mac
- rails
- ruby
- textmate
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090430";}
---
Você usa o Textmate para desenvolvedor em Rails, então deve estar habituado abrir todas as pastas do projeto, com o famoso:

	$ mate .

Mas isso, quando se tem um projeto muuuuuito grande, a pasta public, log, vendo acabar deixando o Textmate um pouco mais lendo. Para acelerar, eu abro apenas as pastas, exceto as mencionadas anteriormente, então:

	$ mate app/ config/ db/ lib/ script/ test/ README Rakefile

Pra isso, fiz um alias:

	$ alias rmate="mate app/ config/ db/ lib/ script/ test/ README Rakefile"

Mas aí começa a vir novos plugins e gems, que criam arquivos/pastas novas que queremos adicionar ao projeto, like RSpec/Capistrano, então, dá-lhe refactoring no alias.

	$ alias rmate="mate app/ config/ db/ lib/ scrpit/ spec/ stories/ test/ README Rakefile Capfile

Agora, estou mudando de projeto, e novas pastas são requeridas e, ao invés de adicionar as pastas/arquivos ao alias, resolvi pensar um pouco mais, então, olha que bonito.

	$ mate $(ls -1 | egrep -v "(log|git|public|vendor|tmp|doc)" | egrep -v .DS_Store)

Agora, basta criar uma função no .bashrc e atualizar meu alias para facilitar a vida, então:

	_rmate() {
	  $ mate $(ls -1 | egrep -v "(log|git|public|vendor|tmp|doc)" | egrep -v .DS_Store)
	}

	alias rmate="_rmate"

Pronto!
