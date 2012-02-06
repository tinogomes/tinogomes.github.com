---
layout: post
title: Testando respostas em RJS
tags:
- ajax
- plugins
- rails
- rjs
- ruby
- teste
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527073";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1324294283";}
  _edit_last: "2440922"
---
Como testar o render desta ação?

{% highlight ruby linenos %}
def minha_acao
  novo_valor = params[:novo_valor]
  render :update do |page|
    page.replace_html "div_valor_total", novo_valor
  end
end
{% endhighlight %}

Simples:

{% highlight ruby linenos %}
def test_minha_acao
  get :minha_acao, :novo_valor => '100.00'
  assert_match Regexp.new("Element.update('div_valor_total', '100.00');"), @response.body
end
{% endhighlight %}

Mas achei um plugin muito legal que ajuda a fazer esses tipos de festa. Vos apresento o [ARTS - Another RJS Testing System](://glu.ttono.us/articles/2006/05/29/guide-test-driven-rjs-with-arts) de [Kevin Clark](://glu.ttono.us/).

Veja como ficaria o código do teste:

{% highlight ruby linenos %}
def test_minha_acao
  get :minha_acao
  assert_rjs :replace_html, :div_valor_total, '100.00'
end
{% endhighlight %}

Na minha opinião, bem melhor! :)

Para instalar o plugin:

1. Ir até a raiz da pasta do projeto
1. Executar: `$ script/plugin discover`
1. Executar: `$ script/plugin install arts`

Maiores detalhes está no [guia](://glu.ttono.us/articles/2006/05/29/guide-test-driven-rjs-with-arts) no próprio blog do Kevin!
