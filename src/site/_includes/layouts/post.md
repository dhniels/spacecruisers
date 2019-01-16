---
layout: layouts/base.njk
pageClass: posts
templateEngineOverride: njk, md
---

<p class="date">
	Published by {{ author }} on <time datetime="{{ date }}">{{ date | dateDisplay }}</time>
</p>
<main>
	{{ content | safe }}
</main>
<p class="date">
	Published by {{ author }} on <time datetime="{{ date }}">{{ date | dateDisplay }}</time>
</p>
