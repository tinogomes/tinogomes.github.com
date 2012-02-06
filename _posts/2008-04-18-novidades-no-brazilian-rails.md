---
layout: post
title: Novidades no Brazilian Rails
tags:
- brazilian_rails
- plugins
- rails
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527059";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1324294276";}
---
Olhando [os tickets do plugin](http://rubyforge.org/tracker/index.php?group_id=4003&amp;atid=15412), resolvi colocar a mão no código para resolver alguns BUGs identificados e solicitações de funcionalidades. Também por e-mail, uma requisição por [Guilherme Garnier](http://ggarnier.wordpress.com/).

Então, o que mudou?

1. Refatoração nos testes de `String`
1. Novas mensagens de erros
1. Acerto na acentuação das constantes `MONTHNAMES` e `DAYNAMES` para `Date` e `Time`
1. Adicionando mais um teste para `titleize`

LEMBRANDO QUE NA PRÓXIMA ATUALIZAÇÃO, SERÁ REMOVIDO OS MÉTODOS `upcase_br` E `downcase_br`, ENTÃO, SE PREPARE.

\:)
