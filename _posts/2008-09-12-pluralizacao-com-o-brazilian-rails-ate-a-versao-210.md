---
layout: post
title: "Pluralização com o Brazilian Rails só até a versão 2.1.0"
tags:
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1231248306";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090453";}
---
A um tempo atrás fiz um post falando [como habilitar a pluralização no Brazilian Rails](http://tinogomes.wordpress.com/2008/09/03/pluralizacao-com-o-brazilian-rails/), agora com a versão em GEMS/PLUGIN.

{% highlight ruby linenos %}
require 'brazilian_rails'
require 'brtraducao/inflector_portuguese'
{% endhighlight%}

Mas um porém:

Isso só funciona até a versão 2.1.0 do Rails, pois a forma de fazer a pluralização a partir do Rails 2.1.1 não usa mais o módulo inflector, mas vamos tentar arrumar isso em breve!
