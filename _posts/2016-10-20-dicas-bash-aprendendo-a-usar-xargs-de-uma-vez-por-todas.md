---
layout: post
title: "[Dicas] Bash - Aprendendo a usar XARGS de uma vez por todas"
description: "Como usar XARGS. How to use XARGS"
category: ""
tags:
  - dicas
  - shell
  - bash
type: post
status: publish
published: true
---
{% include JB/setup %}

Depois da milésia vez [buscando por como usar o `xargs`](http://bfy.tw/4YJ5) resolvi escrever esse post para não precisar mais.

O comando `xargs` é utilizado para, dado uma lista de argumentos, executar um comando passando essa lista como argumento(s) desse comando. Então, você pode juntar todos os itens da lista para serem passados como argumentos de um comando, ou para que se execute um comando por item da lista. Por padrão, cada termo separado por espaço é considerado um item de lista e toda a lista é passada como argumentos para o comando.

Sintaxe com os parâmetros que mais eu uso:

{% highlight Bash %}
command-list | xargs [-0 | -n NUM] [-I NAME] [-p] [command-exec [args]]
{% endhighlight %}

Argumentos | Descrição
--- | ---
`command-list` | Qualquer comando que gere uma lista. Pode ser `ls`, `cat`, `echo`, `find` e etc...
`-0` | Muda o separador padrão para o caracter nulo. Muito útil quando os itens da lista possuem espaço.
`-n NUM` | Pega NUM itens da lista para executar o comando.
`-I NAME` | Dá um nome para o(s) item(ns) a ser passado para o comando.
`-p` | Exibe o comando com os argumentos que serão executados e pede confirmação para executar o comando.
`command-exec [args]` | Comando a ser executado com os argumentos lidos pelo `xargs`. Por padrão, é usado um `echo`

Exemplos:

{% highlight Bash %}
    $ seq -s ' item\n' 3 | xargs
    1 item 2 item 3 item

    $ seq -s ' item\n' 3 | xargs -0
    item 1
    item 2
    item 3

    $ seq -s ' item\n' 3 | xargs -n 1
    1
    item
    2
    item
    3
    item

    $ seq -s ' item\n' 3 | xargs -n 2
    item 1
    item 2
    item 3

    $ seq -s ' item\n' 3 | xargs -n 3
    1 item 2
    item 3 item

    $ seq -s ' item\n' 3 | xargs -p
    /bin/echo 1 item 2 item 3 item?...

    $ seq -s ' item\n' 3 | xargs -INUM echo NUM arg
    1 item arg
    2 item arg
    3 item arg
{% endhighlight %}

Agora espero não mais buscar por isso.

Segue algumas referências que usei:

* <http://www.bosontreinamentos.com.br/linux/certificacao-lpic-1/comando-xargs-construir-e-executar-linhas-de-comando-no-linux/>
* <http://www.cyberciti.biz/faq/linux-unix-bsd-xargs-construct-argument-lists-utility/>
* <http://www.dicas-l.com.br/cantinhodoshell/cantinhodoshell_20070226.php#.WAi-BJMrIy5>
* <https://www.vivaolinux.com.br/dica/Dupla-diabolica-find-e-xargs>
* <https://udgwebdev.com/dicas-de-terminal-processamento-paralelo-com-xargs>
