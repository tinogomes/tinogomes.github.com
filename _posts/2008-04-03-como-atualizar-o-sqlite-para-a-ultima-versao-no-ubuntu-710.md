---
layout: post
title: "Como atualizar o SQLite para a última versão (no Ubuntu 7.10)"
tags:
- linux
- sqlite
- tutorial
- ubuntu
status: publish
type: post
published: true
meta:
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325092506";}
  _edit_last: "2440922"
---
<strong>Como atualizar o SQLite para a última versão (no Ubuntu 7.10) - por Paulo Cassiano</strong>

O <strong>Ubuntu 7.10</strong> inclui em um de seus repositórios de software a versão <em>3.4.2</em> do <strong>SQLite</strong>, base de dados padrão da versão <em>2.x</em> do <em>framework</em> Rails. Para atualizar para a última versão (neste momento, 3.5.7) siga os seguintes passos:

1. Baixe a nova versão:

		$ wget http://sqlite.org/sqlite-3.5.7.tar.gz

1. Descompacte o arquivo com o seguinte comando:

		$ tar -zxvf sqlite-3.5.7.tar.gz

1. Mova-se para o diretório onde os arquivos foram descompactados com o seguinte comando:

		cd sqlite-3.5.7

1. Crie o arquivo _makefile_ com o seguinte comando:

		$ ./configure

1. Faça o _build_ do fonte com o seguinte comando:

		$ make

1. Instale com o seguinte comando:

		$ sudo make install

1.  Teste a instalação com o seguinte comando:

		$ sqlite3.

	O sistema retornará a seguinte saída:

		SQLite version 3.5.7
		Enter ".help" for instructions
		sqlite>

Pronto! Agora você já pode usar o SQLite para criar bases de dados para seus projetos Rails. Você pode sair do shell do SQLite com o seguinte comando:

	sqlite> .e

O SQLite é uma base de dados sensacional naquilo em que se propõe: ser um _BD embarcado_. Grandes e importantes empresas de tecnologia, como a Adobe, a Mozilla Foundation e a Symbian já apostam no chamado [SQLite Consortium](http://sqlite.org/consortium.html) . Vale a pena aprender um pouco mais sobre!

Minhas notas:

Esse tutorial foi publicado por [Paulo Cassiano](http://groups.google.com/groups/profile?hl=pt-BR&amp;enc_user=4WcGNhMAAADKShQdB4KdygVGBZNwRwygWMj6vob75xS36mXc24h6ww) na [lista de discussão do Rails-BR](http://groups.google.com/group/rails-br?hl=pt-BR), através [desse post aqui](http://groups.google.com/group/rails-br/browse_thread/thread/f49f7d6962a88bac?hl=pt-BR#). Fiz alguns ajustes devido a meu ambiente.
