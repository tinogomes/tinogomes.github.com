---
layout: post
title: "Variáveis globais especiais"
tags:
- ruby
- "vari\xC3\xA1vel global"
status: publish
type: post
published: true
meta:
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090364";}
  _edit_last: "2440922"
---
Como sempre esqueço o que é cada tipo de variável global especial, resolvi colocar na minha memória para sempre!

{% highlight ruby linenos %}
$! # Lastest error message

$@ # Location of error

$_ # String last read by `gets`

$. # Line number last read by interpreter

$& # String last matched by regexp

$~ # The last regexo match, as an array of subexpressions

$n # The nth subexpressions in the last match (like as `$~[n]`)

$= # Case-insensitivity flag

$/ # Input record separator

$\ # Output record separator

$0 # The name of the ruby script file

$* # The command line arguments

$$ # Interpretter's process ID

$? # Exit status of last executed child process
{% endhighlight %}

;)

Referência: [Ruby User's Guide - Global variables](http://www.rubyist.net/~slagell/ruby/globalvars.html)
