---
layout: post
title: Mais DRY no seu YAML
tags:
- dry
- yaml
status: publish
type: post
published: true
---
{% include JB/setup %}

Olha quem está vivo? Sim, sou eu. Sem mais enrolação.

Como já publicado no post do [DRY config/database.yml](/2008/03/23/dry-configdatabaseyml), é possível usar _aliases_ para evitar duplicidade de valores, mas como fazer isso para chaves simples? E porque eu tive essa necessidade?

Em uma _view_ onde eu preciso exibir uma mensagem de disponibilidade de expedição de um produto, tenho algo como:

<p style="text-align: center"><strong>app/views/products/show.html</strong></p>

{% highlight erb linenos %}
...
<dl>
  <dt>Prazo para expição</dt>
  <dd><%= I18n.t('.delivery_days', count: product.delivery_days) %></dd>
</dl>
...
{% endhighlight %}

<p style="text-align: center"><strong>config/locales/pt-BR.yml</strong> com repetição</p>

{% highlight yaml linenos %}
pt-BR:
  products:
    show:
      delivery_days:
        one: Pronta Entrega
        other: Disponível em %{count} dias úteis
        zero: Pronta Entrega
{% endhighlight %}

Considerando que eu tenha que mostrar a mensagem quando da disponibilidade de entrega é de zero ou um dia, mas não quero duplicar a mensagem. O que podemos fazer?

Antes da chave que nós queremos "copiar", criamos o _alias_ `&alias_name`, e no lugar do valor que vamos repetir, usamos o `*alias_name`

<p style="text-align: center"><strong>config/locales/pt-BR.yml</strong> sem repetição</p>

{% highlight yaml linenos %}
pt-BR:
  products:
    show:
      delivery_days:
        &oneDeliveryDay one: Pronta Entrega
        other: Disponível em %{count} dias úteis
        zero: *oneDeliveryDay
{% endhighlight %}

No exemplo acima, nós identificamos a chave `:one` com o _alias_ `onDeliveryDay` e aplicanos na chave `:zero`

