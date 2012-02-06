---
layout: post
title: Nova macro para o shoulda
tags:
- github
- rails
- ruby
- shoulda
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1296268105";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090428";}
  _wpas_skip_yup: "1"
  _wpas_skip_twitter: "1"
---
Então, escrevendo testes para o [blogblogs](http://www.blogblogs.com.br), senti a necessidade de uma macro para verificar se o modelo responde a `validates_confirmation_of`. Fiz e já mandei para a galera da thoughtbot, mas caso eles não aceitem, mas queiram pegar essa macro, pode pegar no [meu github](http://github.com/tinogomes). Mas está em um branch separado, então, atenção!

<http://github.com/tinogomes/shoulda>

Como usar:

{% highlight ruby linenos %}
should_require_confirmation_of :attributes # [, :value =>; "some value"] [, :message => "custom message"]
{% endhighlight  %}

Exemplo:

{% highlight ruby linenos %}
class User &lt; ActiveRecord::Base
  validates_confirmation_of :password
  validates_confirmation_of :email, :message => "Please, you wanna confirm your email"
end

class UserTest &lt; Test::Unit::TestCase
  should_require_confirmation_of :password
  should_require_confirmation_of :email, :message => "Please, you wanna confirm your email"
end
{% endhighlight %}

**PS: O bloco acima não foi testado.**
