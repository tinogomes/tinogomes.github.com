---
layout: post
title: Instalando e usando o RDoc-ubiquity
tags:
- ruby
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1294048411";}
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090373";}
---
Fazem alguns meses que [Luiz Cipriani](http://github.com/lfcipriani) lançou uma extensão para Ubiquity, que faz busca em API no formato RDoc. Essa extensão chegou a ser comentada [no podcast](http://www.railsenvy.com/2008/12/10/rails-envy-podcast-episode-058-12-10-2008) da [RailsEnvy](http://www.railsenvy.com).

Cheguei a contribuir um bocadinho assim ó, bem pouquinho e estou usando direto!

Como instalar?

1. Precisa ter [instalado o Ubiquity para Firefox](http://www.open2tech.com/2008/08/30/ubiquity-converse-com-seu-firefox/);
1. Acessar o site do [ubiquity-rdoc](http://projects.talleye.com/ubiquity-rdoc/);
	![Página do RDoc-Ubiquity](/images/posts/picture-5.png)
1. Se você notar, o Ubiquity vai pedir uma confirmação para assinar a extensão;
1. Irá abrir a tela de confirmação para "assinatura" da extensão;
	Lembre-se de marcar a opção de auto-atualização (auto-update);
1. Pressione o botão **I know what I'm doing. Subscribe to it!** (Eu sei o que estou fazendo. Assine!)
1. Pronto para usar!

Como usar?

1. Antes de mais nada, confirme as teclas de atalho para acionar o ubiquity digitando na barra de endereço: [about:ubiquity](ubiquity); No meu caso, é ALT+ESPAÇO
1. Então, quero consulta na API do Rails sobre o método `assert_response`, então digito `rdoc assert_resp` e conforme vou digitando, ele já vai exibindo o resultado.

No próprio site do rdoc-ubiquity, tem a documentação dos comandos, mas para agilizar, vou quebrar seu galho e colocar aqui.

	rdoc <metodo> in <apidoc>

onde:

* metodo - É o nome do método que você quer buscar;
* apidoc - é o nome do alias para a API RDoc, a saber:

Quais APIs estão por padrão?

* rails (padrão - <http://api.rubyonrails.org/>)
* ruby (<http://www.ruby-doc.org/core/>)
* shoulda (<http://dev.thoughtbot.com/shoulda/>)
* factory-girl (<http://dev.thoughtbot.com/factory_girl/>)
* mocha (<http://mocha.rubyforge.org/>)
* rspec_1_1_11 (<http://rspec.rubyforge.org/rspec/1.1.11/>)
* rspec-rails_1_1_11 (<http://rspec.rubyforge.org/rspec-rails/1.1.11/>)

Exemplos:

* rdoc stubs in mocha - Busca pelo método stubs na API do Mocha.
* rdoc ActiveRecord#write - Busca pelo método write da classe ActiveRecord na API do Rails

Espero que essa extensão também seja útil para vocês!
