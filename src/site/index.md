---
title: Space Cruisers
subtitle: A website for Toyota Van owners
layout: layouts/base.njk
---
<script>

</script>

<form action="/search/index.html" method="get">
	<input type="text" id="search-box" name="query">
	<input type="submit" value="search">
</form>

## Latest Posts

<ul class="listing">
{%- for page in collections.post -%}
	<li>
		<a href="{{ page.url }}">{{ page.data.title }}</a> -
		<time datetime="{{ page.date }}">{{ page.date | dateDisplay }}</time>
	</li>
{%- endfor -%}
</ul>
