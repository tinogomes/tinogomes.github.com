---
layout: post
title: "Usando Git Hook para fazer análise do código"
description: "Neste post, eu mostro como estou usando git hook para fazer análise dos códigos que foram preparados para commit, com Brakeman, Robocop, RubyCritic e Rails Best Practices"
category: ""
tags:
  - dicas
  - git
  - ruby
type: post
status: publish
published: true
---
{% include JB/setup %}

Senta que lá vem história.

Atualmente temos algumas ferramentas online, como [Code Climate][codeclimate] e [Codacy][codacy], para fazer análise do código do nosso projeto, em busca de falhas de segurança, duplicação de código e etc. Também estamos diante da possibilidade de levantar um servidor de [CI][ci], como o [jenkins][jenkins], e configurar para fazer o mesmo processo. Usando essas ferramentas, nossos códigos são avaliados somente após feito o commit e enviado (`git push`) para o repositório "central". No caso, havendo algum problema no resultado dos testes, podemos ser somos notificados por e-mail e, sendo isso parte do fluxo do CI, teoricamente, nossas últimas atualizações serão um bloqueio para continuar nosso trabalho em outra coisa.

Eu tenho preferido passar essas ferramentas antes de fazer o commit, aproveitando que estou com a mente fresca com as minhas últimas atualizações, ficando mais fácil resolver o problema detectado por alguma dessas ferramentas.

Com isso, resolver colocar o _git hook_ `pre_commit`. No caso em questão, estou em um projeto Ruby on Rails e nele estão configurados algumas ferramentas de análise de código, como [`brakeman`][brakeman], [`rucobop`][rubocop], [`rails_best_practices`][rbp] e [`rubycritic`][rubycritic].

Segue abaixo o hook pre-commit:

<script src="https://gist.github.com/tinogomes/4bd4344d72ccd133cb0dc5059ceaac24.js"></script>

Outras referências:

* <https://infinum.co/the-capsized-eight/top-8-tools-for-ruby-on-rails-code-optimization-and-cleanup>

[codeclimate]: https://codeclimate.com/
[codacy]: https://www.codacy.com/
[jenkins]: http://jenkins-ci.org/
[brakeman]: http://brakemanscanner.org/
[rubocop]: https://github.com/bbatsov/rubocop
[rbp]: http://rails-bestpractices.com/
[rubycritic]: https://github.com/whitesmith/rubycritic
[ci]: http://www.martinfowler.com/articles/continuousIntegration.html
