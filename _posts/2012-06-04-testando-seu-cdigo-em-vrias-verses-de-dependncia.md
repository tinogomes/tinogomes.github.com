---
layout: post
title: "Testando seu código em várias versões de dependência"
tags: [ruby rake bundler]
status: publish
published: true
---
{% include JB/setup %}

Preciso verificar se o [Brazilian Rails](https://github.com/tapajos/brazilian-rails/) funciona em várias versões do [Rails](https://github.com/rails/rails/), 2.3.x, 3.0.x, 3.1.x e 3.2.x e [Ruby](http://ruby-lang.org/) 1.8.7 e 1.9.x. Como faz?

Com [RVM](https://rvm.io/), seria:

    $ rvm 1.8.7@rails23x,1.8.7@rails30x,1.8.7@rails31x,1.8.7@rails32x,[até],1.9.3@rails32x rake

Claro, existe um script automatizando isto, mas ainda sim é feio d+.

Uma solução, seria usar o [infinity\_test](https://github.com/tomas-stefano/infinity_test), mas o Brazilian Rails tem testes em TestUnit e também em [RSpec](http://github.com/rspec/rspec) e como o infity\_test é para execução em apenas um "ambiente", não sei se irá funcionar (não testei)

Outra é usar o [Appraisal](https://github.com/thoughtbot/appraisal), que se integra com o Bundler e Rake, o que fica bastante flexível.

Seguindo os passos conforme indicado no README do projeto, no meu ambiente fico com apenas um gemset por versão de Ruby.

    $ rvm 1.8.7@brazilianrails,1.9.1@brazilianrails,1.9.2@brazilianrails,1.9.3@brazilianrails rake test_spec

Para quem não separa as instalações por gemset, usando apenas o default, fica ainda mais limpo.

    $ rvm 1.8.7,1.9.1,1.9.2,1.9.3 rake test_spec

E se seguir a sugestão de David Czarneck, basta criar uma tarefa Rake,

{% highlight ruby linenos %}
# Rakefile
desc "Ruby test units and RSpec"
task :test_spec do
  Rake::Task.execute["test"]
  Rake::Task.execute["spec"]
end

desc "Runs tests on Ruby 1.8.7 and 1.9.2"
task :test_all do
  system "rvm 1.8.7@brazilianrails,1.9.1@brazilianrails,1.9.2@brazilianrails,1.9.3@brazilianrails rake test_spec"
end
{% endhighlight %}

e executar:

    $ rake test_all

Referências:

* <http://blog.agoragames.com/blog/2011/05/27/testing-multiple-ruby-versions-and-gemsets-using-rvm/>