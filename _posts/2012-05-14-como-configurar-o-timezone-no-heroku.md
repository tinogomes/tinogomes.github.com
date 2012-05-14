---
layout: post
title: "Como configurar o timezone no Heroku"
tags: [heroku]
status: publish
published: true
---
{% include JB/setup %}

Basta apenas adicionar uma configuração, em uma variável de ambiente

	$ heroku config:add TZ=America/Sao_Paulo
	Adding config vars and restarting app... done, v24
	  TZ => America/Sao_Paulo
	$ heroku run console
	Running console attached to terminal... Time.oup, run.1
	Time.now
	irb(main):001:0> Time.now
	=> 2012-05-14 09:51:51 -0300

A [lista de timezones disponíveis](http://en.wikipedia.org/wiki/List_of_tz_database_time_zones) está na Wikipedia.

Referências:

* <http://tamersalama.com/2010/10/05/heroku-timezone-adjustment/>
* <http://clarkli.wordpress.com/2011/12/29/set-timezone-on-heroku-servers/>
