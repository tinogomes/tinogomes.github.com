---
layout: post
title: "Nova série: \"Eu não sabia que...\""
tags:
- dicas
- "eu n\xC3\xA3o sabia que"
- ruby
- singleton
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090449";}
---
Ao peger uma instância de um objeto qualquer e adicionar dinâmicamente um método a esta instância, ela se torna um singleton.

	$ irb
	>> o = Object.new
	=> #<Object:0x393cbc>
	>> def o.name; puts 'Tino Gomes'; end
	=> nil
	>> o.singleton_methods
	=> ["name"]

Legal, não? Não! [Ah! tá, me dixculpa.](http://www.youtube.com/watch?v=hca3bX1zpyY) :/
