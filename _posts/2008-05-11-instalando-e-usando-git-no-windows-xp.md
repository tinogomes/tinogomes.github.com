---
layout: post
title: Instalando e usando Git no Windows XP
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
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1313438862";}
---
Extraído de [desde guia](http://github.com/guides/using-git-and-github-for-the-windows-for-newbies)

Existem duas formas de instalar o Git no Windows. Uma é instalando o [cygwin](http://www.cygwin.com/) e então o [Git](http://git.or.cz/). Mas a forma mais fácil é com [msysGit](http://code.google.com/p/msysgit/).

Então os passos são:

1. [Baixe o instalador](http://code.google.com/p/msysgit/downloads/list). Hoje está na [versão 1.5.5 Beta](http://msysgit.googlecode.com/files/Git-1.5.5-preview20080413.exe)

	<img src="/images/posts/instalando_git_no_windows_001.png" alt="instalando_git_no_windows_001" />

1. Next

	<img src="/images/posts/instalando_git_no_windows_002.png" alt="instalando_git_no_windows_002" />

1. Next

	<img src="/images/posts/instalando_git_no_windows_003.png" alt="instalando_git_no_windows_003" />

1. Next

	<img src="/images/posts/instalando_git_no_windows_004.png" alt="instalando_git_no_windows_004" />

1. Next

	<img src="/images/posts/instalando_git_no_windows_005.png" alt="instalando_git_no_windows_005" />

1. Next

	<img src="/images/posts/instalando_git_no_windows_006.png" alt="instalando_git_no_windows_006" />

1. Aqui você decide o modo de instalação. O modo <strong>Use Git Bash only</strong> instala o console 'Linux', fazendo com que você use o Git apenas por este ambiente. O modo <strong>Run Git from the Windows Command Prompt</strong> permite você executar o Git no próprio console do Windows (Eu não gostei). O Modo <strong>Run Git and included Unix tools from the Windows Command Prompt</strong>, permite não só usar o Git no Prompt do Windows, como também adicionar algumas ferramentas nativas do Linux.

	<img src="/images/posts/instalando_git_no_windows_007.png" alt="instalando_git_no_windows_007" />

1. Aguade...

	<img src="/images/posts/instalando_git_no_windows_008.png" alt="instalando_git_no_windows_008" />

1. Na falta de Next, Finish! : )

	<img src="/images/posts/instalando_git_no_windows_009.png" alt="instalando_git_no_windows_009" />

1. Após a instalação, encontre no Menu Iniciar o atalho. <strong>Git Bash</strong> é o console "Linux". <strong>Git GUI</strong> é uma interface para auxiliar o gerenciamento de projetos. Eu particulamente, prefiro usar o console.

	<img src="/images/posts/instalando_git_no_windows_010.png" alt="instalando_git_no_windows_010" />

1. Aqui o console "Linux" aberto. Nas telas abaixo, eu mostro como instalar o plugin [Brazilian Rails](http://brazilian-rails.rubyforge.org/). Quando sair a versão 2.1 do Rails, o modo de instalação será nativo pelo script/plugin install. Mas enquanto não é...

	Lembre-se de configurar seu nome e e-mail, assim que abrir o console. Para isso digite os comandos:

		$ git config --global user.name 'Fulano de Tal'
		$ git config -- global user.email seu@email.com

	<img src="/images/posts/instalando_git_no_windows_011.png" alt="instalando_git_no_windows_011" />

	<img src="/images/posts/instalando_git_no_windows_012.png" alt="instalando_git_no_windows_012" />

	<img src="/images/posts/instalando_git_no_windows_013.png" alt="instalando_git_no_windows_013" />

	<img src="/images/posts/instalando_git_no_windows_014.png" alt="instalando_git_no_windows_014" />

	<img src="/images/posts/instalando_git_no_windows_015.png" alt="instalando_git_no_windows_015" />

	<img src="/images/posts/instalando_git_no_windows_016.png" alt="instalando_git_no_windows_016" />

	<img src="/images/posts/instalando_git_no_windows_017.png" alt="instalando_git_no_windows_017" />

	<img src="/images/posts/instalando_git_no_windows_018.png" alt="instalando_git_no_windows_018" />

Se tiver alguma coisa errada, ou que eu tenha esquecido de falar, mandem seus comentários!
