---
layout: post
title: "Busca em campos de texto passando valores numéricos no MySQL"
description: ""
category: ""
tags:
- MySQL
type: post
status: publish
published: true
---
{% include JB/setup %}

> <cite>Como em toda casa de ferreiro, nem sempre o espero é de ferro.</cite>

Em nosso dia a dia, as vezes precisamos fazer umas intervenções via console do Rails e, com isso, temos alguns métodos auxiliares para fazer tarefas simples, porém rotineiras.

Entre essas rotinas, fazemos busca de uma conta através do e-mail de um usuário e então atualizamos a informação necessária. Como as vezes temos somente o e-mail do usuário, precisamos fazer uma busca do usuário pelo e-mail e, dado o usuário, obtemos a lista de contas e então, temos a conta para fazer o ajuste. Outras vezes já temos o ID da conta a ser ajustada, o que agiliza o processo. Para auxiliar essa busca, estava criando mais um método para encontrar a conta, dado o e-mail do usuário, algo como:

{% highlight ruby linenos %}
# ./lib/console_helpers.rb
module ConsoleHelper
  def update_info(id_or_email, new_data = {})
    account = Account.find_by_id(id_or_email)
    unless account
      user = User.find_by_email!(id_or_email)
      raise "User have more than 1 account: #{user.account_ids}" if user.accounts.count > 1
      account = user.accounts.first
    end
    account.update_info(new_date)
    puts "New data for account##{account.id}: #{new_date.inspect}"
  end
end

# ./config/application.rb
console do
  Rails::ConsoleMethods.send :include, ::ConsoleHelpers
end
{% endhighlight %}

Neste caso, quando entro no console, posso facilmente fazer:

    => update_info 'johndoe@domain.com', {attribute: 'new_value'}
    New data for account #123: {:attribute => 'new_value'}

Porém, fazendo os testes no console (após os testes automatizados, claro!), ao passar um número de ID que não existia (número zero), fui surpreendido com a atualização de uma conta que eu não esperava.

    => update_info 0, {attribute: 'new_value'}
    New data for account #456: {:attribute => 'new_value'}

O que notei, foi que a busca do MySQL retornou um usuário, cujo o e-mail dele era `00022e34f23a72@domain.com`, pois a query SQL criada foi:

     SELECT `users`.* FROM `users` WHERE `users`.`email` = 0 ORDER BY email ASC LIMIT 1;

Ou seja, o MySQL tem o mesmo comportamento do Ruby, ao tentar converter uma string para número.

    => '102-string'.to_i # results: 102
    102
  
Logo, fiz o ajuste na função para converter para string na busca por e-mail.

{% highlight ruby linenos %}
# ./lib/console_helpers.rb
module ConsoleHelper
  def update_info(id_or_email, new_data = {})
    account = Account.find_by_id(id_or_email)
    unless account
      user = User.find_by_email!(id_or_email.to_s)
      raise "User have more than 1 account: #{user.account_ids}" if user.accounts.count > 1
      account = user.accounts.first
    end
    account.update_info(new_date)
    puts "New data for account##{account.id}: #{new_date.inspect}"
  end
end
{% endhighlight %}


Não caia da mesma armadilha.