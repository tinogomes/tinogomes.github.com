---
layout: post
title: "Pluraliza\xC3\xA7\xC3\xA3o com o Brazilian Rails?"
tags:
- brazilian_rails
- gems
- rails
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527045";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1313438844";}
---
Após o [lançamento oficial](http://blog.improveit.com.br/articles/2008/08/31/saiu-o-brazilian-rails-2-0) da nova versão do [Brazilian Rails](http://www.improveit.com.br/software_livre/brazilian_rails) em gems, o [Akita](http://www.akitaonrails.com/) acabou ["twittando"](http://twitter.com/AkitaOnRails/statuses/906208737) com dúvida sobre como usar a pluralização na nova versão. [Respondi](http://twitter.com/tinogomes/statuses/906211629) mas vou corrigir aqui.

Após instalado o Brazilian Rails `$ gem install brazilian-rails` para habilitar a pluralização:

{% highlight ruby linenos %}
require 'brazilian_rails'
require 'brtraducao/inflector_portuguese'
{% endhighlight %}

Então, foi mal a resposta anterior Akita! ;)
