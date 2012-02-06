---
layout: post
title: como remover branch remoto no git
tags:
- git
- git-branch
- git-push
- git-remote
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  jabber_published: "1299499864"
  _wpas_done_twitter: "1"
  _wpas_done_yup: "1"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1322732188";}
  _wpas_skip_fb: "1"
---
Esse post é mais para lembrete, pois muitas vezes esqueço como remover um branch remoto, enfim...

Tem o modo que é inesquecível, pelo menos para mim:

	$ git push origin :old_branch_to_be_deleted

Mas caso você queira remover um branch que tenha o mesmo nome de uma TAG, temos a seguinte resposta de retorno:

	$ git push origin :v0.2.1
	error: dst refspec v0.2.1 matches more than one.
	error: failed to push some refs to 'git@github.com:tinogomes/resque_spec.git'

Neste caso, ao invés de só usarmos o nome do branch, devemos usar o seu endereço de referência, no caso:

	$ git push origin :refs/heads/v0.2.1

Referência: <http://cheat.errtheblog.com/s/git>
