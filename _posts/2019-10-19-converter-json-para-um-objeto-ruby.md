---
layout: post
title: "Converter JSON para um Objeto Ruby"
tags:
  - ruby
status: publish
type: post
published: true
---
{% include JB/setup %}

Quem nunca quis validar um JSON usando as validações do ActiveModel do Rails? Mas transformar um JSON multinível em um objeto Ruby parece ser um passo chato de realizar, né? Bom, hoje eu descobri que não.

<p style="text-align: center"><strong>Exemplo de um JSON bem simples</strong></p>

{% highlight json linenos %}
{
  "id": "740b3e24-8686-48b6-9eb0-1b09d04bf18e",
  "name": "Carl Johnson",
  "document": "12345",
  "addresses": [
    {
      "street": "414, East 137th Street",
      "neiborhood": "Compton",
      "city": "Los Angeles",
      "state": "CA",
      "zipcode": "90061"
    }
  ]
}
{% endhighlight %}

<p style="text-align: center"><strong>Importando o JSON para uma classe</strong></p>

{% highlight ruby linenos %}
class AccountFromJson < OpenStruct
  include ActiveModel::Validations

  validates :name, :document, presence: true
end


json = File.read('./any/path/file.json')
account = JSON.parse json, object_class: AccountFromJson

account.valid? # => true
account.name # => "Carl Johnson"
account.addresses[0].street # => "414, East 137th Street"
{% endhighlight %}

Ah, e Também funciona se no JSON for um array.

Pois é, quem diz que macaco velho não aprende "novos" truques?

Referências:

* [Convert a complex nested hash to an object](https://coderwall.com/p/74rajw/convert-a-complex-nested-hash-to-an-object)
* [Converting JSON to an Object in Ruby](https://medium.com/@somethvictory/converting-json-to-an-object-in-ruby-e64e6acf8a3b)

