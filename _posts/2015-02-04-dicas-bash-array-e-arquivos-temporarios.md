---
layout: post
title: "[Dicas] Bash - Usando Array e criando arquivos temporários"
description: "Neste post eu mostro duas boas dicas de usar array a várias variáveis e criar arquivos temporários"
category: ""
tags: [bash]
status: publish
published: true
---
{% include JB/setup %}

As dicas abaixo foram extraídas do post [10 tips for writing efficient Bash scripts][efficient].

## Usar Array em lugar de múltiplas variáveis

Ao invés de criar muitas variáveis para valores em um mesmo contexto.

{% highlight Bash linenos %}
color1='Red'
color2='Green'
color3='Blue'

echo $color1
echo $color2
{% endhighlight %}

Crie um array.

{% highlight Bash linenos %}
$colors=('Red' 'Green' 'Blue')

echo ${colors[0]}
echo ${colors[1]}
{% endhighlight %}


## Criar arquivos/diretórios temporários

Precisa de um arquivo temporário? Use `mktemp` para criar arquivos ou diretórios temporários.

{% highlight Bash linenos %}
tempfile=$(mktemp)
tempdir=$(mktemp -d)

echo $tempfile
echo $tempdir
{% endhighlight %}


**PS: No FreeBSD (OSX), tem que passar um template para o nome do arquivo/diretório**

[efficient]: http://hacktux.com/bash/script/efficient "10 tips for writing efficient Bash scripts"
