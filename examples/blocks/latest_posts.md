# Latest post

```html
<div class="latest_posts">
	<ul>
		{ com_keys (
			id: '{{ component_id }}',
			description: 'Latest posts',
			htmlElement: 'li',
			html:'
				<a href="{{ page.url }}">{{ keys.title }}</a>
			',
			limit: '10',
			sortBy:'publishedDate descending'
		) }
	</ul>
</div>
```
