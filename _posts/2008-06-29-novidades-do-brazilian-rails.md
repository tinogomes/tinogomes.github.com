---
layout: post
title: Novidades do Brazilian Rails
tags:
- brazilian_rails
- plugins
- rails
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090470";}
---
Como muitos já sabem, [estamos refatorando o plugin Brazilian Rails](http://blog.improveit.com.br/articles/2008/06/21/o-futuro-do-brazilian-rails), para torná-lo um [conjunto de gems](http://blog.improveit.com.br/articles/2008/06/23/agora-%C3%A9-a-hora), não perdendo a opção de instalar como plugin.

Nesse meio tempo, estou lendo o livro [RailsSpace](http://railsspace.com/), onde me deparei com um exemplo da view de perfil de usuario, conforme o trecho abaixo:

{% highlight erb linenos %}
<div class="form_row">
  <label for='gender'>Sexo:</label>
  <%= radio_button :spec, :gender, 'M' %>Masculino
  <%= radio_button :spec, :gender, 'F' %>Feminino
</div>
{% endhighlight %}

Notaram algo que talvez muitos fazemos para cadastro de pessoas? É, isso mesmo! Seleção de sexo.

Então, no meio dessa bagunça, implementamos mais dois helpers.

{% highlight erb linenos %}
<%= select_sexo :spec, :gender %>
==>
<%= radio_button(:spec, :gender,'M') %> Masculino
<%= radio_button(:spec, :gender, 'F') %> Feminino

<%= radio_button_sexo :spec, :gender %>
==>
<%= select :sexo, :spec, [['Masculino', 'M'], ['Feminino', 'F']] %>
{% endhighlight %}

Veja como ficaria o exemplo do livro:

{% highlight erb linenos %}
<div class="form_row">
  <label for='gender'>Sexo:</label>
  <%= radio_button_sexo :spec, :gender %>
</div>
{% endhighlight %}

Em breve, mais novidade... E continuem acompanhando pelo twitter... :)
