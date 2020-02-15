---
layout: post
title: "Metaprogramação em Ruby - Criando métodos de Classe"
description: ""
category:
tags:
  - ruby
status: publich
type: post
published: true
---
{% include JB/setup %}

Nem falo nada sobre quanto tempo sem escrever nada, mas vou contar uma novidade rapidinha: Agora [Gaveteiro][gaveteiro] virou [NEI][nei]. Mas vamos ao que interessa nesse post.

Métodos de Classe? Bom, sabemos que isso não existe em Ruby. Na verdade são métodos _singleton_ da classe, mas enfim, vamos abistrair essa parte.

Bom, então, digamos que você vai mapear um recurso de uma API e ela tem um campo/atributo `type`, e essa pode retornar os valores _ClientA.administrador_, _ClientA.manager_ e _ClientA.buyer_ como valores para este atributo. Mas você quer ter um código mais limpo, algo que você possa perguntar ao seu objeto: `resource.admin?` em vez de ficar espalhado pelo seu código algo como `resource.type == "ClientA.administrador"` e etc. E o mesmo para criar uma instância desse objeto, teria que fazer algo como `Resource.new(type: 'ClientA.administrador')`. Não seria melhor ter algo como `Resource.new_admin(...)`?. Nesse caso, vou apresentar dois métodos para criar dinamicamente métodos. o `define_method` serve para criar os métodos de instância e o `define_singleton_method` para criar os "métodos de classe".

{% highlight ruby linenos %}
class Resource < OpenStruct
  include ActiveModel::Validations

  TYPES = {
    "admin"   => "ClientA.administrator",
    "manager" => "ClientA.manager",
    "buyer"   => "ClientA.buyer"
  }.freeze

  validates :api_id, presence: true
  validates :type, inclusion: TYPES.values

  TYPES.each do |key, value|
    # define "question" methods for each type (e.g.: def admin?; type == "ClientA.administrador"; end)
    define_method "#{key}?" do
      type == value
    end

    # define constructors for each type (e.g.: Resource.new_admin({...}))
    self.define_singleton_method("new_#{key}".to_sym) do |**args|
      new(args.merge(type: value))
    end
  end
end
{% endhighlight %}

Então agora, é só usar

{% highlight ruby %}
resource = Resource.new_admin
resource.type   # => it returns "ClientA.administrator"
resource.admin? # => it returns true
resource.buyer? # => it returns false

resource = Resource.new_buyer(name: "Tino")
resource.type   # => it returns "ClientA.buyer"
resource.admin? # => it returns false
resource.buyer? # => it returns true
resource.name   # => it returns "Tino" - YOU DON'T SAY?
{% endhighlight %}

O que achou?

> PS1: Claro que ainda estamos limitados a conhecer todos os valores que virão no atributo `type`. Se quisermos que seja 100% dinâmico... (Será que rola outro post?)
>
> PS2: Deu para perceber que desde o último post, estou fazendo integrações com APIs.

Referências:
* [Stackoverflow - How to dynamically define a class method which will refer to a local variable outside?](https://stackoverflow.com/questions/3487403/how-to-dynamically-define-a-class-method-which-will-refer-to-a-local-variable-ou)
* [Medium Ruby Inside <3 - Class Methods Are Singleton Methods](https://medium.com/rubyinside/class-methods-in-ruby-a-thorough-review-and-why-i-define-them-using-class-self-af677ede9596)

[gaveteiro]: https://www.gaveteiro.com.br
[nei]: https://www.nei.com.br
