---
layout: post
title: Rails - Testes funcionais com cookie
tags:
- cookie
- rails
- ruby
- test
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1298691183";}
  _wpas_done_yup: "1"
  _wpas_done_twitter: "1"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1324475095";}
---
No meu `ApplicationController`, coloquei um `before_filter` que verifica se no cookie do usuário tem uma chave e verifico seu valor. No caso de não existir o valor, ou o mesmo for diferente do esperado, eu mando um `reset_session` e adiciono a chave com o valor. Até aí beleza. Quando fui rodar minha bateria de testes... BOOM! Estourou um monte de erros nos testes funcionais de admin, já que os mesmos adicionam a sessão um usuário que tem regra de admin, como no exemplo abaixo.

{% highlight ruby linenos %}
class Admin::BlogsControllerTest < ActionController::TestCase
  setup do
    @admin = Factory(:user, :role => "admin")
    @request.session[:user_id] = @admin.id
  end
  #...
end
{% endhighlight %}

Bastaria adicionar no setup de cada arquivo de teste funcional uma simples linha:

{% highlight ruby linenos %}
setup do
  #...
  @request.cookies['chave'] = 'valor'
end
{% endhighlight %}

Mas pensei comigo mesmo: <a href="http://pt.wikipedia.org/wiki/Ruby_on_Rails#DRY"><abbr title="Don't Repeat Yourself">DRY</abbr></a>. Logo, em meu test/test_helper.rb

{% highlight ruby linenos %}
class ActionController::TestCase
  setup :setting_cookie_version
  def setting_cookie_version
    @request.cookies['_bbsession_version'] = APP_CONFIG['session']['version']
  end
end
{% endhighlight %}
