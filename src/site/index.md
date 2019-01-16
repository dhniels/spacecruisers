---
title: Space Cruisers
subtitle: A website for Toyota Van owners
layout: layouts/base.njk
---
<script>

</script>

<form action="/search/index.html" method="get">
	<input type="text" id="search-box" name="query" placeholder="Search for a post...">
	<input type="hidden" value="submit">
</form>

## Latest Posts

<ul class="listing">
{%- for page in collections.post | reverse -%}
	<li>
		<a href="{{ page.url }}">{{ page.data.title }}</a> -
		<time datetime="{{ page.date }}">{{ page.date | dateDisplay }}</time>
	</li>
{%- endfor -%}
</ul>
