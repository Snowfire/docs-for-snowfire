#Latest post

### HTML

```html
<div class="latest_posts">
	<ul>
		{ com_keys (
			id:'201',
			syncId:'200',
			description:'Latest posts',
			htmlElement:'li',
			html:'
				<a href="{{ page.url }}">{{ keys.title }}</a>
			',
			limit: '10',
			sortBy:'publishedDate descending'
		) }
	</ul>
</div>

```
