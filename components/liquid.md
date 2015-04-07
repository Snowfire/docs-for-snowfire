# Liquid

This is for version 2. [Version 1](legacy/liquid1.md)

```xml
{ com_liquid2 ( id:'1', description:'Enter text', code:'' ) }
```

## Parameters

* `code` (text)
* `selectablePage` (boolean)

## `code`

### Variables

* `page` - Current page.
* `selectedPage` - Selected page.
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

```javascript
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
```javascript
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

```javascript
{{ page.next.publishDate | stringToDateFormat:"%B %e, %Y" }}
```
