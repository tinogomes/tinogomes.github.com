---
layout: default
---
{% include JB/setup %}

{% assign posts = site.posts %}

<dl class="posts">
{% if posts.size > 0 %}
	{% for post in posts %}
	  <dt class="title">
			<a href="{{ BASE_PATH }}{{ post.url }}" class="title" rel="post">{{ post.title }}</a>
			<span>{{ post.date | date_to_string }}</span>
		</dt>
		<dl class="link">
			<a href="{{ BASE_PATH }}{{ post.url }}" class="link" rel="post">{{ BASE_PATH }}{{ post.url }}</a>
		</dl>
	{% endfor %}
{% endif %}
</dl>
