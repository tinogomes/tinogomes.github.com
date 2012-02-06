---
layout: post
title: Como instalar o plugin Exception Notification
tags:
- expection
- mail
- rails
- ruby
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527074";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1229527075";}
  _edit_last: "2440922"
---
Já uso este plugin em alguns projetos e queria adicionar ele em um outro, mas não lembrava o endereço do reposotório. Fui ao bom e velho [Tio Google](://www.google.com.br), mas a busca não foi tão fácil quanto gostaria, então resolvi simplificar e publicar aqui!

Para instalar o plugin, digite no console:

	$ ruby script/plugin install http://dev.rubyonrails.com/svn/rails/plugins/ exception_notification

Se seu projeto está é armazenado em um repositósio [SVN](://www.google.com.br/url?sa=t&amp;ct=res&amp;cd=3&amp;url=http%3A%2F%2Fpt.wikipedia.org%2Fwiki%2FSubversion&amp;ei=vhp9R8e4N4mgeu7m0Do&amp;usg=AFQjCNHQjCqm9NBVA4Icy2e0t_FOuQDgGg&amp;sig2=Eeqs3HPrl1YKI9CRODjVMg) e você quer adicionar o plugin como external, basta adicionar o parametro `-x`, conforme exemplo abaixo :

	$ ruby script/plugin install -x http://dev.rubyonrails.com/svn/rails/plugins/ exception_notification

Para configurar, basta você [dar uma olhadinha no post](://www.nomedojogo.com/2007/05/22/receba-erros-do-seu-software-por-email/) do [Carlos Brando](://www.workingwithrails.com/person/8137-carlos-brando) (Já tá virando sócio :) )
