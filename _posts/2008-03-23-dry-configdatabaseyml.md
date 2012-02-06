---
layout: post
title: DRY config/database.yml
tags:
- config
- database
- dicas
- dry
- rails
- ruby
- yaml
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527065";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1229527065";}
  _edit_last: "2440922"
---
Sempre esqueço como fazer um database.yml limpo, então resolvi publicar.

{% highlight yaml linenos %}
login: &login
  adapter: mysql
  username: username
  password: password
  host: mysql.example.com

development:
  <<: *login
  database: app_dev

test:
  <<: *login
  database: app_test

production:
  <<: *login
  database: app_prod
{% endhighlight %}

Este exemplo foi extraído [aqui](http://snippets.dzone.com/posts/show/2263).
