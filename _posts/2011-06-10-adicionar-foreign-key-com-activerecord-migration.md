---
layout: post
title: Adicionar Foreign key com ActiveRecord Migration
tags:
- activerecord
- belogns_to
- migration
- rails
- references
- ruby
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  jabber_published: "1307709584"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1322148109";}
  _wpas_done_twitter: "1"
---
Sempre que vou fazer um model passando os campos (sim, vez enquando faço assim, e?) sempre fico na dúvida da cláusula para gerar a foreign key, se é no singular ou plural que se escreve, enfim... Para eu não esquecer mais (assim espero) o uso é "[referenceS](http://apidock.com/rails/ActiveRecord/ConnectionAdapters/Table/references)", mas olhando na documentação do [Rails](http://guides.rubyonrails.org/), me deparei com um alias para esta mesma opção, que no caso fica mais fácil ainda lembrar "[belongs_to](http://apidock.com/rails/ActiveRecord/ConnectionAdapters/Table/belongs_to)", isso mesmo, então...

	$ rails g model post title:string body:text category_id:integer
	$ rails g model post title:string body:text category:references
	$ rails g model post title:string body:text category:belongs_to

É tudo farinha do mesmo saco. :)

That's all folks!!!
