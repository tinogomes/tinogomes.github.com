---
layout: post
title: ssh-copy-id no Mac OS X
tags:
- mac
- ssh
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1299376590";}
  _wpas_done_yup: "1"
  _wpas_done_twitter: "1"
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090344";}
---
Eu iria escrever toda uma história explicando porque desse script, mas desisti. Só quero agradecer ao [MV](http://twitter.com/darthmv) pela dica e o script está aí, para copiar sua chave ssh pública para um servidor e fazer acesso ssh sem ter que digitar senha do usuário.

**arquivo ssh-copy-id**

{% highlight bash linenos %}
#!/bin/sh

KEY="$HOME/.ssh/id_rsa.pub"

if [ ! -f $KEY ];then
  echo "private key not found at $KEY"
  echo "* please create it with "ssh-keygen -t dsa" *"
  echo "* to login to the remote host without a password, don't give the key you create with ssh-keygen a password! *"
  exit
fi

if [ -z $1 ];then
  echo "Please specify user@host.tld as the first switch to this script"
  exit
fi

echo "Putting your key on $1... "

KEYCODE=`cat $KEY`
cat $KEY | ssh $1 "cat - >> ~/.ssh/authorized_keys"

echo "done!"
{% endhighlight %}

Logo, para mandar sua chave para o servidor, basta:

	$ ssh-copy-id usuario@endereco_ou_ip_do_servidor

Claro, você terá que digitar a senha do usuário do servidor pela última vez, se tudo funcionar...

Ah! [Minha busca no google foi essa](http://www.google.com/search?client=safari&amp;rls=en&amp;q=ssh-copy-id+osx&amp;ie=UTF-8&amp;oe=UTF-8).
