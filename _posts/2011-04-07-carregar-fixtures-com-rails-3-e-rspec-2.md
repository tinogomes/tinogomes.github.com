---
layout: post
title: Carregar fixtures com Rails 3 e RSpec 2
tags:
- fixtures
- rails
- rails3
- rake
- rspec
- rspec2
- ruby
status: publish
type: post
published: true
meta:
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090329";}
  _edit_last: "2440922"
  jabber_published: "1302184849"
  _wpas_done_yup: "1"
  _wpas_done_twitter: "1"
  _wpas_done_fb: "1"
---
Sim, ainda temos fixtures e no **RSpec 2**, não temos mais a `rake` para carregar as fixtures `spec:db:fixtures:load`, mas podemos fazer com a tarefa `db:fixtures:load`, apenas carregando a variável de ambiente `FIXTURES_PATH` com o caminho relativo ao diretório de fixtures do **RSpec**.

	$ FIXTURES_PATH="spec/fixtures" rake db:fixtures:load
