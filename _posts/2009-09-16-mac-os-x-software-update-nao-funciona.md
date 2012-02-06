---
layout: post
title: "Mac OS X Software Update não funciona"
tags:
- apple
- mac os x
- software update
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1298699433";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090349";}
---
Quando ainda estávamos na Webco, meu MacBook foi configurado para pegar as atualizações de nosso servidor interno. Até então funcionava e era bem rápido, pois como o servidor fazia o download de todas as atualizações para si, quando nossos Mac Books iam fazer os devidos updates, usava essa cópia local e ficava bem mais rápido o update. Mas devido as mudanças que ocorreram, "perdemos" nosso servidor central de updates e como minha máquina apontava para esta, não mais conseguia fazer os updates. Mas nada que um começo de férias para resolver esse problema. Resolvi solucionar esse problema e não foi fácil achar a solução, então resolvi colocar aqui para quem precisar.

[Ná pagina de suporte da apple, onde descreve para configurar conforme descrevi acima](http://support.apple.com/kb/HT3765), tinha o que eu queria que era o endereço para o catalogo, mas o bendito arquivo **/etc/swupd/swupd.plist** não existia. Como faz? Busca prá lá... busca pra cá... Até que cheguei em outra página que explica [como configurar o Software update sem o Open Directory](http://krypted.com/mac-os-x/mac-os-x-setting-a-software-update-server-without-open-directory/), onde cheguei até o arquivo **/Library/Preferences/com.apple.SoftwareUpdate.plist**, no qual era só trocar o endereço do atributo **CatalogURL** para um servidor local, mas eu queria trocar para o servidor original, logo...

1. Abrir o **Property List Editor**

	[!Property List Editor](http://tinogomes.files.wordpress.com/2009/09/property-list-editor-1-open.png)

1. Abrir o arquivo */Library/Preferences/com.apple.SoftwareUpdate.plist*

	[!Property List Editor - Openning a file](http://tinogomes.files.wordpress.com/2009/09/property-list-editor-3-open-a-file.png)

1. Editar o attributo <tt>CatalogURL</tt> com o valor "<tt>http://swscan.apple.com/content/catalogs/index.sucatalog<!--/t-->"</tt>

	[!Property List Editor - Editing CatalogURL attribute](http://tinogomes.files.wordpress.com/2009/09/property-list-editor-4-edit-catalogurl-attribute.png)
