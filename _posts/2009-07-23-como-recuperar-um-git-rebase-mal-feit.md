---
layout: post
title: Como recuperar um git rebase mal feito
tags:
- cherry-pick
- git
- rebase
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  _wp_old_slug: recuperando-um-git-rebase-mal-feit
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1298691153";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090359";}
---
Como [acabei de "twittar"](http://twitter.com/tinogomes/status/2791755806), fiz <del datetime="2009-07-23T04:05:14+00:00">cagada</del> bagunça em um branch ao usar o [git rebase](http://www.kernel.org/pub/software/scm/git/docs/git-rebase.html). Antes de me desesperar, resolvi fazer [a velha busca no "Pai"](http://www.google.com.br/search?hl=pt-BR&amp;q=recover+git+rebase&amp;btnG=Pesquisa+Google&amp;meta=&amp;aq=f&amp;oq=) (termo usado para identificar o [Google](http://www.google.com.br) pelo famosíssimo [Guanabara](http://www.guanabara.info/sobr/) em um dos [guanacasts](http://www.guanabara.info/category/casts/podcast/guanacast-podcast/) sobre SEO ([parte I](http://www.guanabara.info/2009/04/guanacast-61-tecnicas-de-seo-parte-i/) e [ parte II](http://www.guanabara.info/2009/05/guanacast-62-tecnicas-de-seo-parte-ii/)), onde encontrei [um post de Greg DeVore](http://bluemangolearning.com/blog/2009/03/recovering-from-a-disastrous-git-rebase-mistake/), explicando como recuperar uma <del datetime="2009-07-23T04:05:14+00:00">cagada</del> bagunça dessa. E com meus MAD SKIILS, ainda usei o [git cherry-pick](http://www.kernel.org/pub/software/scm/git/docs/git-cherry-pick.html) para recuperar o commit perdido. Lembrando que deve haver forma mais higiênica de recuperar um commit "perdido". Bom, chega de bla-bla-bla e vamos ao que interessa. (os hashes de commit foram abreviados para facilitar a leitura)

	$ echo NÃO SE DESESPERAR
	NÃO SE DESESPERAR
	$ cat .git/logs/refs/meu-branch
	937 a0e tino ...commit: meu commit 2
	a0e 1eb tino ...commit(amend): meu commit 2
	1eb 8db tino ...rebase (finish): refs/heads/meu-branch onto 8db
	$ echo NOTE QUE NO COMMIT "1eb" FOI O ÚLTIMO ANTES DO rebase
	NOTE QUE NO COMMIT "1eb" FOI O ÚLTIMO ANTES DO rebase
	$ git cherry-pick -n 1eb
	Finished one cherry-pick.
	$ git status
	...
	modified app/controller/application_controller.rb
	...
	$ git commit -m 'meu commit 2'
	[meu-branch 3f5f542] meu commit 2
	15 files changed, 157 insertions(+), 21 deletions(-)

Pronto, seu trabalho foi recuperado!
