---
layout: post
title: "Atualiza\xC3\xA7\xC3\xA3o do Brazilian Rails"
tags:
- brazilian_rails
- rails
- ruby
status: publish
type: post
published: true
meta:
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1313438895";}
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527063";}
  _edit_last: "2440922"
---
Seguindo a sugestão de [Guilherme Garnier](http://ggarnier.wordpress.com/) e o patch enviado por ele, ocorreram as seguintes novidades:

1. Adicionado os métodos `upcase`, `upcase!`, `downcase`, `downcase!`, `titleize`, `titleize!`, `nome_proprio!` para palavras acentuadas
1. ALERTA de DEPRECATION para os métodos `upcase_br` e `downcase_br`.
1. Ajuste no método `nome_proprio`, identificado pelo Guilherme

Em breve a [página inicial](http://brazilian-rails.rubyforge.org/) do plugin e a [API](http://brazilian-rails.rubyforge.org/api/) online serão atualizadas, pois ainda estou no trabalho (22:42) e estou partindo pra casa. hehehe

## update #1

O Guilherme enviou no patch os métodos `capitalize_each_word` e `capitalize_each_word!`, mas foi renomeado para o `titleize` e `titleize!`, pois se propõe a mesma funcionalidade já existente no Rails!
