Latest posts
============

This isn't a real component, we just juse com_keys to create a ul/li list of the 5 latest blog posts


```html
	{ com_keys (
	    id:'{{ component_id }}',
	    syncId:'{{ sync_id }}',
	    description:'Latest posts',
	    htmlElement:'li',
	    html:'
	         <a href="{{ page.url }}">{{ keys.title }}</a>
		',
		limit: '5',
	    sortBy:'publishedDate descending'
	) }
```