---
layout: post
title: Instalando e usando Git no Windows XP - SE
tags:
- git
- msysgit
- tutorial
- windows
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090475";}
---
Bom pessoal, como vocês sabem, [escrevi este tutorial](http://tinogomes.wordpress.com/2008/05/11/instalando-e-usando-git-no-windows-xp/), explicando como instalar o Git no Windows. Mas [Urubatam](http://www.urubatan.com.br/) [lembrou muito bem](http://groups.google.com/group/rails-br/browse_thread/thread/2be35523e3e78e6f?hl=pt-BR) sobre a dificuldade de algumas pessoas de visualizar as telas e até mesmo para o [google](http://www.google.com.br) indexar o tutorial.

Então, aqui vou tentar fazer o mesmo tutorial de modo textual.

Como já disse, esse tutorial foi baseado na minha experiência em instalar o Git na minha casa! É isso mesmo, eu ainda uso Windows em casa! Usei [esse tutorial](http://github.com/guides/using-git-and-github-for-the-windows-for-newbies) como referência.

1. Baixe o versão mais atual do [msysGit](http://code.google.com/p/msysgit/downloads/list): (Até o momento, está na [versão 1.5.5 Beta](http://msysgit.googlecode.com/files/Git-1.5.5-preview20080413.exe))
1. Praticamente, é o padrão NNF de instalação;
1. Na quinta tela, você decide o modo de instalação. O modo **Use Git Bash only** instala o console "Linux", fazendo com que você use o Git apenas por este ambiente. O modo **Run Git from the Windows Command Prompt** permite você executar o Git no próprio console do Windows (Eu não gostei). O Modo **Run Git and included Unix tools from the Windows Command Prompt**, permite não só usar o Git no Prompt do Windows, como também adicionar algumas ferramentas nativas do Linux.
1. Após a instalação, encontre no Menu Iniciar / Programas / Git os atalhos. **Git Bash** é o console "Linux". **Git GUI** é uma interface para auxiliar o gerenciamento de projetos. Eu particulamente, prefiro usar o console.
1. Com o console "Linux" aberto, lembre-se de configurar seu nome e e-mail, assim que abrir o console. Para isso digite os comandos:

		$ git config --global user.name 'Fulano de Tal'
		$ git config — global user.email seu@email.com

1. Vamos instalar o plugin do [Brazilian Rails](http://brazilian-rails.rubyforge.org/)? (Olha o merchan... :P)
1. Com o console aberto, encontre a pasta do plugins do seu projeto. Digamos que seu projeto esteja em **d:\projetos\meu_projeto**, então digite:

		$ cd /d/projetos/meu_projeto/vendor/plugins

1. Então faça o clone do projeto.

		git clone git://github.com/tapajos/brazilian-rails

1. Pronto!
