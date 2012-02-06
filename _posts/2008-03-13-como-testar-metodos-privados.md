---
layout: post
title: "Como testar m\xC3\xA9todos privados?"
tags:
- ruby
- spec
- teste
status: publish
type: post
published: true
meta:
  delicious: a:3:{s:5:"count";s:1:"1";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1229527068";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1229527069";}
  _edit_last: "2440922"
---
Hoje, no blog [Nome do Jogo](://www.nomedojogo.com/) de [Carlos Brando](://workingwithrails.com/person/8137-carlos-brando), saiu um [post falando sobre como testar métodos privados](://www.nomedojogo.com/2008/03/12/como-testar-um-metodo-privado/). Uma outra maneira é tornar todos os métodos públicos, sem adicionar nenhum outro.

Basta adicionar o trecho abaixo em seu arquivo test/test_helper.rb ou spec/spec_helper.rb

{% highlight ruby linenos %}
def turn_public_methods clazz
  clazz.class_eval do
    private_instance_methods.each { |instance_method| public instance_method }
    private_methods.each { |method| public_class_method method }
  end
end
{% endhighlight %}

Um exemplo:

{% highlight ruby linenos %}
#File spec/my_model_spec.rb
require File.dirname(__FILE__) + '/../spec_helper'
describe MyModel do
  before(:each) do
    turn_public_methods(MyModel)
    @mymodel = MyModel.new
  end

  describe "Verify a private method" do
    @mymodel.private_method_name.should_not be_nil
  end
end
{% endhighlight %}

## Atualização #1

Conforme o comentário de [Rafael Muller](://queroseragil.wordpress.com/author/queroseragil/), resolvi adicionar a comparação apresentada por [Evan Phoenix](://blog.fallingsnow.net/) e esta solução.

{% highlight ruby linenos %}
### Versão do Evan
class NinjaTest &lt; Test::Unit::TestCase
  def test_should_punish_sloppy_coders
    @ninja = Ninja.new
    def @ninja.flog_publicly(*args)
      kill(*args)
    end
    assert_equal "3 victims are no longer with us.", @ninja.flog_publicly(3)
  end
end

### Versão do Tino ;)
class NinjaTest &lt; Test::Unit::TestCase
  def setup
    turn_methods_public(Ninja);
  end

  def test_should_punish_sloppy_coders
    @ninja = Ninja.new
    assert_equal "3 victims are no longer with us.", @ninja.kill(3)
  end
end
{% endhighlight %}

Para mim, um pouco mais limpo o teste, mas gosto é gosto! :)
