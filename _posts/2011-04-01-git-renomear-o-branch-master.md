---
layout: post
title: "Git: Renomear o branch 'master'"
tags:
- git
- git-branch
- git-checkout
- git-push
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  jabber_published: "1301669063"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090330";}
  _wpas_done_yup: "1"
  _wpas_done_twitter: "1"
  _wpas_done_fb: "1"
---
Digamos que seu projeto vai ganhar uma reescrita, uma refatoração pesada, atualização do framework (rails 2 para rails 3) ou qualquer coisa que vá mudar o rumo do seu código de forma revolucionária. Enfim, cria-se um novo branch e começa a brincadeira. Neste tempo, seu master continua com atualizações, com correções de bugs, novos features, enfim, sua aplicação ainda está viva. Quando terminado o processo de refatoração, o merge com o branch principal, normalmente o master, acaba sendo uma dor de cabeça e a opção adotada algumas vezes é tornar o branch de refactoring no branch principal. Para este caso, vou explicar como renomear o branch de refactoring para o master e, claro, guardar o master para poder fazer 'a caça as bruxas' depois. Vou usar como base que estamos atualizando a versão do Rails 2 para Rails 3.

1. Vá para um branch qualquer, se não tiver, crie um;

		$ git branch temp
		$ git checkout temp

1. Renomear o branch master para rails2;

		$ git branch -m master rails2

1. Renomear o branch de rails3 para o master;

		git branch -m rails3 master

1. Remover o branch master remoto;

		$ git push origin :master

1. Criar o branch master no repositório remoto;

		$ git push origin master:refs/heads/master

1. Criar o branch rails2 no reposotório remoto;

		$ git push origin rails2:refs/heads/rails2

1. Remover o branch rails3 no repositório remoto;

		$ git push origin :rails3

Pronto, teoricamente quando a galera fizer o git pull, pegará o novo branch, mas eu recomento que remova o branch master local de cada máquina e pegar novamente;

	$ git branch temp
	$ git checkout temp
	$ git branch -d master
	$ git checkout -b master origin/master

Fontes:
* <http://www.dmo.ca/blog/20080307124544/>
* <http://www.kernel.org/pub/software/scm/git/docs/git-branch.html>
* <http://www.kernel.org/pub/software/scm/git/docs/git-checkout.html>
* <http://www.kernel.org/pub/software/scm/git/docs/git-push.html>
