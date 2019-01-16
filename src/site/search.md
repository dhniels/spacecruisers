---
title: Search
layout: layouts/base.njk
---

<form action="/search/index.html" method="get">
	<label for="search-box">Search</label>
	<input type="text" id="search-box" name="query">
	<input type="submit" value="search">
</form>

<ul id="search-results"></ul>

<script>
  window.store = {
		{%- for post in collections.post -%}
		  "{{ post.url }}": {
		    "url": "{{ post.url }}",
		    "title": "{{ post.data.title }}",
		    "content": "{{ post.templateContent | striptags | escape }}"
		  }{% if not loop.last %},{% endif %}
		{%- endfor -%}
  };
</script>
<script src="/js/lunr.js"></script>
<script src="/js/search.js"></script>
