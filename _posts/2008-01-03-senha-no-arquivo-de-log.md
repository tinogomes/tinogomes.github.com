---
layout: post
title: Senha no arquivo de log
tags:
- log
- rails
- ruby
- "seguran\xC3\xA7a"
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1246374544";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1246374545";}
  _edit_last: "2440922"
---
Relembrando o [post](://www.nomedojogo.com/2007/08/16/todo-mundo-pode-ver-minha-senha-nos-arquivos-de-log-do-rails/) de [Carlos Brando](://workingwithrails.com/person/8137-carlos-brando) em seu [blog](://www.nomedojogo.com/), vou aproveitar para incrementar um pouco mais ;)

Você não gostaria de encontrar isso no seu arquivo de log:

	Processing AcessoController\#login (for 10.0.0.1 at 2007-11-13 18:01:05) [POST]
	Session ID: 65f5dff4cb6382df7ff867058577577b
	Parameters: {"commit"=>"Submit", "action"=>"login", "controller"=>"access", "login"=>"user.name", "password"=>"SENHA_DO_USUARIO"}
	Redirected to http://www.mydomain.com/
	Completed in 0.01000 (100 reqs/sec) | DB: 0.00000 (0%) | 302 Found [http://www.mydomain.com/login]

Olha que lindo, a senha é **SENHA_DO_USUARIO**, muito bem protegido, não?

Então, para solucionar esse problema, coloque o filtro no seu controller. (eu sugiro o <code>ApplicationController</code>)

{% highlight ruby linenos %}
class ApplicationController < ActionController::Base
  #...
  filter_parameter_logging :senha, :password
  #...
end
{% endhighlight %}

O que isso faz? Bom, qualquer campo que contenha os termos <code>/senha|password/1</code>

Tem mais na [API](://api.rubyonrails.org/classes/ActionController/Base.html#M000441).
