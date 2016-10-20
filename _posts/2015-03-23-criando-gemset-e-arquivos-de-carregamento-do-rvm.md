---
layout: post
title: "Criando gemset e arquivos de carregamento do RVM"
description: ""
category: ""
tags:
  - ruby
  - rvm
status: publish
published: true
---
{% include JB/setup %}

Essa é mais para ficar para lembrança do que uma dica, mas enfim, sempre que vou começar um novo projeto em [Ruby][ruby], eu costumo a usar o [RVM][rvm] (sim, ainda o RVM) e gosto de separar os projetos por [gemsets][gemsets] (sim, isso também ocupa mais espaço).

Para criar um novo gemset, na versão do Ruby correta e os arquivos de carregamento automático, executo o comando abaixo:

{% highlight Bash %}
$ rvm 2.2.1@project_name --create --ruby-version
{% endhighlight %}

Pronto!

[ruby]: https://www.ruby-lang.org/en/
[rvm]: https://rvm.io/
[gemsets]: https://rvm.io/gemsets
