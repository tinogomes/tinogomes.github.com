---
layout: post
title: "Criando branches no git muito mais rápido"
description: ""
category: ""
tags: 
  - dicas
  - bash
  - git
  - git-branch
type: post
status: publish
published: true
---
{% include JB/setup %}

Cansei de criar git branches assim:

`$ git checkout -b fix/some_bugfix_with_long_name`

Agora é só:

`$ fix-branch some bugfix with long name`

Segue abaixo minhas novas funções bash:

{% highlight shell linenos %}
    function fix-branch() {
        local new_branch_name=$(echo "$*" | tr " " _)
        git checkout -b fix/$new_branch_name
    }

    function feature-branch() {
        local new_branch_name=$(echo "$*" | tr " " _)
        git checkout -b feature/$new_branch_name
    }
{% endhighlight %}
