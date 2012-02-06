---
layout: post
title: Task rake para habilitar/desabilitar portuguese inflection no Brazilian Rails
tags:
- brazilian_rails
- pluralize
- rails
- rake
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"1";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527051";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090471";}
---
De vez em quando, surge alguém com o problema de:

* Não consigo habilitar as inflexões em português no Brazilian Rails!

Ontem foi a gota d'água e hoje, resolvi escrever uma task rake para habilitar/desabilitar esta funcionalidade no aplicativos quando estiver com o Brazilian Rails.

Então, que já está usando o Rails, a partir da versão 2.0.2 já pode aproveitar essa funcionalidade. Então agora, basta:

	$ rake brazilianrails:inflector:portuguese:check
	$ rake brazilianrails:inflector:portuguese:disable
	$ rake brazilianrails:inflector:portuguese:enable

Para quem ainda está as versões anteriores a 2.0.2, basta no arquivo de envorinment.rb, após o bloco de iniciação da aplicação, adicionar `require 'inflection_portuguese'`, conforme abaixo:

{% highlight ruby linenos %}
Rails::Initializer.run do |config|
...
end
require 'inflector_portuguese' # <<<==== Adicionar esta linha!!! :)
{% endhighlight %}

Espero que desse "problema" ninguém mais sofra! :)
