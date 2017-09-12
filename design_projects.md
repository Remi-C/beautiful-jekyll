---
layout: page
title: Design projects
subtitle: Some of my design projects
---

Here is a list of my design projects.

<div class="posts-list">
  {% for post in site.posts %}
	  {% if post.tags contains "design" %}
	  <article class="post-preview">
		<a href="{{ post.url | prepend: site.baseurl }}">
		  <h2 class="post-title">{{ post.title }}</h2>

		  {% if post.subtitle %}
		  <h3 class="post-subtitle">
			{{ post.subtitle }}
		  </h3>
		  {% endif %}
		</a>

		<p class="post-meta">
		  Posted on {{ post.date | date: "%B %-d, %Y" }}
		</p>

		<div class="post-entry-container">
		  {% if post.image %}
		  <div class="post-image">
			<a href="{{ post.url | prepend: site.baseurl }}">
			  <img src="{{ post.image }}">
			</a>
		  </div>
		  {% endif %}
		  <div class="post-entry">
			{{ post.excerpt }} 
		  </div>
		</div>

		{% if post.tags.size > 0 %}
		<div class="blog-tags">
		  Tags:
		  {% if site.link-tags %}
		  {% for tag in post.tags %}
		  <a href="{{ site.baseurl }}/tag/{{ tag }}">{{ tag }}</a>
		  {% endfor %}
		  {% else %}
			{{ post.tags | join: ", " }}
		  {% endif %}
		</div>
		{% endif %}

	   </article>
	  {% endif %}
  {% endfor %}
</div>

{% if site.total_pages > 1 %}
<ul class="pager main-pager">
  {% if site.previous_page %}
  <li class="previous">
    <a href="{{ site.previous_page_path | prepend: site.baseurl | replace: '//', '/' }}">&larr; Newer Posts</a>
  </li>
  {% endif %}
  {% if site.next_page %}
  <li class="next">
    <a href="{{ site.next_page_path | prepend: site.baseurl | replace: '//', '/' }}">Older Posts &rarr;</a>
  </li>
  {% endif %}
</ul>
{% endif %}