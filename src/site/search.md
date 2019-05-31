---
title: Search
layout: layouts/base.njk
---
<style> #search-results li {list-style-type: none; border-bottom: 1px solid rgba(255,255,255,.3);} </style>

<form action="/search/index.html" method="get">
	<!-- <label for="search-box">Search</label> -->
	<input type="text" id="search-box" name="query">
	<!-- <input type="submit" value="search" style="min-width:auto;"> -->
	<input type="hidden" value="submit">
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
