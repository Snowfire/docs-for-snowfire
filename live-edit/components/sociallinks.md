Social links
============

Creates a ul/li list of links and icons to different social media websites

```html
{ com_sociallinks(
	id:'{{ component_id }}',
	description:'Social links',
	htmlElement:'ul'
	class:'sociallinks',
	caption:'false',
	itemHtml:'
		<li>
			<a href="%url%">
				<img src="/themes/clean/public/images/ui/%service%_icon.png" alt="%service%">
			</a>
		</li>
	'
) }
```