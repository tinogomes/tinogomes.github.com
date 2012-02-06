---
layout: post
title: rake com argumentos
tags:
- rake
- ruby
- tutorial
status: publish
type: post
published: true
meta:
  _edit_last: "2440922"
  delicious: a:3:{s:5:"count";s:1:"0";s:9:"post_tags";s:0:"";s:4:"time";s:10:"1294327216";}
  reddit: a:2:{s:5:"count";s:1:"0";s:4:"time";s:10:"1325090365";}
---
{% highlight ruby linenos %}
desc "Say hi. Use USER environment variable as default"
  task :hi, :user do |t, args|
  args.with_defaults(:user => ENV["USER"])

  puts "Hi #{args[:user]}!"
end
{% endhighlight %}

Código disponível em <http://gist.github.com/130194>

logo:

	$ echo $USER
	celestino

	$ rake hi
	(in /Users/celestino)
	Hi celestino!

	$ USER=tino rake hi
	(in /Users/celestino)
	Hi tino!

	$ rake hi USER=tino2
	(in /Users/celestino)
	Hi tino2!

	$ rake hi[tino3]
	(in /Users/celestino)
	Hi tino3!

Fonte: <http://nhw.pl/wp/2008/10/11/rake-and-arguments-for-tasks>
