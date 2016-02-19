# Liquid

This is for version 2. [Version 1](legacy/liquid1.md)

```xml
{ com_liquid2 ( id:'1', description:'Enter text', code:'' ) }
```

## Parameters

* `code` (text)
* `selectablePage` (boolean)
* `siblingTags` (boolean)

## `code`

### Variables

* `page` - Current page.
* `selectedPage` - Selected page.
* `siblingTags` - Array of tags for all sibling (i.e other blog posts).
* `keys` - Contains `tagsFilter`.

### Page

Propterties on a page / collection of pages:

* `children`
* `rootPath`
* `root`
* `tags`
* `name`
* `id`
* `url`
* `publishDate`
* `components`
* `count`
* `older`
* `newer`
* `previous`
* `next`
* `previousSibling`
* `keys`

### Liquid filters

#### tagToUrl

Example:

```
{ com_liquid2 (
	id:'1', 
	description:'Tags', 
	code:'
	    	{% for page.tags as tag %}
    			<a href="{{ tag | tagToUrl:page }}">{{ tag }}</a>
    		{% end_for %}
	')
}
```


#### monthToNumeric


#### html

Runs a `html_entity_decode()` on the value, useful when working with com_image and the html parameter

Example:
```
<div>
	{ com_liquid2 (
		id:'1', 
		description:'Next article', 
		code:'
			{% if page.next %}
				{ page.next.keys.main_image | html }}
			{% end_if %}
		')
	}
</div>
```

#### stringToDateFormat

Converts a date string to a specific format (see http://se2.php.net/strftime)

```
{{ page.next.publishDate | stringToDateFormat:"%B %e, %Y" }}
```


### Examples


#### Show all tags on the main blog layout

```
{ com_liquid2 (
	id:'1', 
	description: 'Tags', 
	selectablePage:'false', 
	code:'

		{% if keys.tagsFilter != empty %}
			<h1>Current tag: {{ keys.tagsFilter | join:"," | capitalize }}</h1>
		{% end_if %}
		
		{% if page.children.tags != empty %}
			<div>
			
				{% if keys.tagsFilter != empty %}
					<div>
						<a href="{{ "" | tagToUrl:page }}">Show all posts</a>
					</div>
				{% end_if %}
			
				<ul>
					{% for page.children.tags as tag %}
						<li>
							<a href="{{ tag | tagToUrl:page }}">{{ tag }}</a>
						</li>
					{% end_for %}
				</ul>
			</div>
		{% end_if %}
' ) }
```

#### Show all tags on the blog on a specific blog post

```
{ com_liquid2 (
    id:'1', 
    description: 'Tags', 
    selectablePage: 'false', 
    siblingTags: 'true',
    code:'
	{% for siblingTags as tag %}
		<li>
    			<a href="{{ tag | tagToUrl:page }}">{{ tag }}</a>
		</li>
	{% end_for %}
') }
```

