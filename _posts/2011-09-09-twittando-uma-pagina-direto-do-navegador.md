---
layout: post
title: "Twittando uma página direto do navegador (atualizado em 30/09/2021)"
tags:
- geral
- tweet this
- twitter
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  jabber_published: "1315580091"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090227";}
  _wpas_done_twitter: "1"
  tagazine-media: a:7:{s:7:"primary";s:83:"/images/posts/screen-shot-2011-09-09-at-11-43-34.png";s:6:"images";a:2:{s:83:"/images/posts/screen-shot-2011-09-09-at-11-43-34.png";a:6:{s:8:"file_url";s:83:"/images/posts/screen-shot-2011-09-09-at-11-43-34.png";s:5:"width";s:3:"695";s:6:"height";s:3:"365";s:4:"type";s:5:"image";s:4:"area";s:6:"253675";s:9:"file_path";s:0:"";}s:66:"/images/posts/tweet-this-button.png";a:6:{s:8:"file_url";s:66:"/images/posts/tweet-this-button.png";s:5:"width";s:3:"565";s:6:"height";s:3:"260";s:4:"type";s:5:"image";s:4:"area";s:6:"146900";s:9:"file_path";s:0:"";}}s:6:"videos";a:0:{}s:11:"image_count";s:1:"2";s:6:"author";s:7:"2440922";s:7:"blog_id";s:7:"2362964";s:9:"mod_stamp";s:19:"2011-09-09 14:54:50";}
---
**Atualizado em 30/09/2021** : Por algum motivo que não me lembro agora, removi o repositório no Github que continha o código do Tweet This, então agora esse post está válido. Segue o post:

As vezes, quando estamos navegando e paramos em uma página que gostaríamos de [twittar](http://www.portuguesnarede.com/2010/04/tuitar-x-twittar-o-retorno.html), mas a mesma não tem um botão para divulgação e você não tem nenhuma extensão/plugin no seu navegador integrada a sua conta do twitter, o jeito é copiar/colar o link em seu cliente de [twitter](http://twitter.com), descrever a que se refere o link e então compartilha com seus seguidores.

Bom, esse era meu cenário e cansei. Então resolvi usar um modo que já uso para adicionar links em ~~meu delicious~~ e resolvi fazer algo similar para o twitter.

<a href="javascript:window.open('https://twitter.com/intent/tweet?original_referer='+document.domain+'&ref_src=TweetThis&text='+document.title+'&url='+document.URL);void(0);"><img class="size-full wp-image-464" src="/images/posts/screen-shot-2011-09-09-at-11-43-34.png" width="590" height="309" />Tweet this</a>

Basta arrastar o link da imagem acima "Tweet this" para os bookmarks do seu navegador (sugiro que seja na seção que ficam visíveis na barra) e quando estiver na página que deseja twittar, clique neste bookmark e ele vai abrir uma nova janela com a página do twitter, com o campo de tweet preenchido com o link mais o título da página. Claro, requer que sua seção de twitter esteja logada ;)

<img class="alignnone size-full wp-image-465" title="tweet-this-button" src="/images/posts/tweet-this-button.png" alt="" width="565" height="260" />

<!-- javascript:window.open('https://twitter.com/intent/tweet?original_referer='+document.domain+'&ref_src=TweetThis&text='+document.title+'&url='+document.URL);void(0); -->
