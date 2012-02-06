---
layout: default
---
{% include JB/setup %}

{% assign archieve = site.posts %}
{% assign first_post = archieve.first %}

{% if archieve.size > 0 %}
<header>
	<h1><a href="{{ first_post.url }}">{{ first_post.title }}</a></h1>
</header>

<aside class="meta">
	<dl>
		<dt>Publicado em:</dt>
		<dd>{{ first_post.date | date: '%d/%m/%Y' }}</dd>
		<dt>Tags:</dt>
		<dd>
			{% for tag in first_post.tags %}
					<a href="{{ BASE_PATH }}{{ site.JB.tags_path }}#{{ tag }}-ref">{{ tag }}</a>
			{% endfor %}
		</dd>
	</dl>
  <nav class="share">
  	<div class="twitter-tweet"><a href="https://twitter.com/share" class="twitter-share-button" data-count="horizontal" data-via="{{ site.author.twitter }}" data-lang="pt" data-url="{{ first_post.url }}">Tweet</a></div>
  </nav>
</aside>

<div class="content">
	{{ first_post.content }}
	<a id="more" href="{{ first_post.url }}#disqus">Comments &raquo;</a>
</div>
{% endif %}

{% if archieve.size > 1 %}
<h2>Posts mais antigos</h2>
<ul class="posts">
	{% for post in archieve %}
		{% if post != first_post %}
			<li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
		{% endif %}
	{% endfor %}
</ul>
{% endif %}