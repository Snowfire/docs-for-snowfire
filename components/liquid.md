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

	{% for page.tags as tag %}
		<a href="{{ tag | tagToUrl }}">{{ tag }}</a>
	{% end_for %}

#### monthToNumeric