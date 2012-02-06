---
layout: post
title: "Plugin para Integra\xC3\xA7\xC3\xA3o Cont\xC3\xADnua on Rails"
tags:
- agil
- agile
- improve it
- integracao continua
- plugins
- rails
- ruby
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527070";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1314586591";}
  _edit_last: "2440922"
---
O pessoal da [Improve It](://www.improveit.com.br), como sempre, trazendo coisas boas para a comunidade. Eles extraíram de uma funcionalidade que usamos a muito tempo, um plugin, que foi batizado de [Integration](://integration.rubyforge.org/).

Veja mais detalhes em <http://integration.rubyforge.org/>

Uma pequena tradução:

## O que é o plugin Integration?

Integration é um plugin para projetos em [Ruby on Rails](://www.rubyonrails.org/) que disponibiliza tasks para automatizar todos os passos para o [processo síncrono de integração contínua](://jamesshore.com/Blog/Why%20I%20Dont%20Like%20CruiseControl.html), sendo, [integração contínua](://martinfowler.com/articles/continuousIntegration.html) sem um servidor como [CruiseControl](://cruisecontrol.sourceforge.net/)! Por que? Porque é dessa forma que gostamos de fazer!

## Para instalar:

	$ ruby script/plugin install -x svn://rubyforge.org/var/svn/integration

## Após instalar, basta:

	$ rake integrate

## Dependências:

* [Subversion](http://subversion.tigris.org)
* [Hpricot](http://code.whytheluckystiff.net/hpricot) (optional)
* [Rcov](http://eigenclass.org/hiki.rb?rcov) (optional)
* [Selenium on Rails](http://selenium-on-rails.openqa.org) (optional)
* [RSpec](http://rspec.info) (optional)
