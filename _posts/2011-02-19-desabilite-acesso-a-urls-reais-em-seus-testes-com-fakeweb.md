---
layout: post
title: Desabilite acesso a URLs reais em seus testes com Fakeweb
tags:
- fakeweb
- rails
- rspec
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  jabber_published: "1298090756"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090337";}
  _wpas_done_yup: "1"
  _wpas_done_twitter: "1"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1299468209";}
---
Em um dos projetos que estou trabalhando atualmente, a suite de testes começou a demorar a executar, papo de 5 minutos. Então, habilitando a opção de profile do [RSpec](http://github.com/rspec) para identificar quais testes estavam lentos, identifiquei que eram os testes referentes a importação de feeds. Então, o que descobri? Que na verdade, os testes estavam fazendo requisições reais dos feeds. Então, primeiro passo é, desabilitar acesso a URLs reais e nada como o bom e velho [Fakeweb](http://fakeweb.rubyforge.org/) para ajudar nessa parte.

Dois passos simples

No Gemfile:

{% highlight ruby linenos %}
gem "fakeweb", :group =&gt; :test
{% endhighlight %}

E no spec/spec_helper.rb:

{% highlight ruby linenos %}
FakeWeb.allow_net_connect = false
{% endhighlight %}

Agora toda a suite roda em 30 segundos. Claro, próximo passo é arrumar os testes que estão quebrando e nesse caso. MOCK NELES!
