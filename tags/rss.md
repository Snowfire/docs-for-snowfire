# RSS Feed

```html
{ com_rss (
	id:'{{ component_id_0 }}',
	description: 'RSS',
	itemHtml: '
		<li>
			<a href="{{ link }}" target="_new">
				<span class="date">{{ pubDate | date: "%Y-%m-%d" }}</span>
				{{ title }}
			</a>
		</li>
	',
	htmlElement: 'ul',
	limit: '5'
) }
```

## Different date styles

`{{ pubDate | date: "%Y-%m-%d %H:%M:%S" }}` = 2014-10-28 14:43:00
`{{ pubDate | date: "%e %b %Y" }}` = 28 Oct 2014
	
## Source

It is possible to output the feed source with `{{ source }}`. Might be useful with JS manipulation to show the website name.