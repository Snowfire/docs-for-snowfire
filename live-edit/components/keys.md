# Keys

Keys are made for doing things such as blogs where you need to automatically link pages to a list. Keys are set on components with the parameter `key`. A key could be thought of as a name for that component.

In `com_keys`, either the user selects some pages, or they are set for them with parameters. From these pages keys are extracted, and used to present some form of list. This could be used to pull a headline (singlerow) and the lead paragraph (wysiwyg) to a blog post list.

## Bloglist.tpl

This would be the page to where all blog posts are pulled. The `html` parameter is rendered for every page selected, and the pages are sorted by `published date` in `descending` order, in the example below.

Liquid syntax is used in the `html` parameter. Some variables set by Snowfire and the keys you have defined, are available. Variables set by Snowfire are in the `page` namespace, e.g. `{{ page.url }}`. Keys are in the keys namespace, e.g. `{{ keys.myOwnKey }}`.

In the example below `{{ page.url }}`, `{{ page.name }}` and `{{ page.publishDate }}` are Snowfire variables, while `{{ keys.body }}` is a key.

```
{ com_keys ( 
    id:'1', 
    description:'Bloglist',
    html:'<h1><a href="{{ page.url }}">{{ page.name }}</a></h1><h2>{{ page.publishDate }}</h2>{{ keys.body }}',
    sortBy:'publishedDate descending'
) }
```

## Blogpost.tpl

In this example, this is the page layout from where the keys are pulled. **Please note** that keys cannot be used on components in repeaters.

```
{ com_wysiwyg ( 
    id:'1', 
    description:'Body',
    key:'body' 
) }
```

Make sure you open pages created with blogpost.tpl, click the Live edit component and hit Save after you've added the key parameter to an existing component, to generate the key.

## Parameters

### `html`

The HTML code to be rendered for every page pulled. Liquid syntax is used. If you want to know all available keys, write `<pre>{{ keys }}</pre>`.

Don't forget that Liquid allows for conditional statements etc:


```
{% if keys.image %}
	{{ keys.image }}
{% else %}
	No image available
{% endif %}
```

* `{{ page.url }}` - Url to the current page from where the keys are pulled.
* `{{ page.name }}` - Page name of the current page from where the keys are pulled.
* `{{ page.id }}` - A unique identifier for the page.
* `{{ page.html }}` - The page HTML. **Must be enabled with the parameter `enablePageHtml`.**
* `{{ page.publishDate }}` - Publish date of the current page from where the keys are pulled. See the format function for formatting options.
  Example with formatting: `{{ page.publishDate | format:"%e %h %Y" }}`
* Any user-defined key. Keys are set on components with the key parameter. In the above example, the wysiwyg component in layout Blogpost.tpl has key body. To get this key, use `{{ keys.body }}`.


### `sortBy`

What order the pages should be rendered in.

* `pageName ascending/descending`
* `createdDate ascending/descending`
* `updatedDate ascending/descending`
* `publishedDate ascending/descending`


### `contentType`

Set it to "page" to enable more flexible keys (specific pages or tags)


### `functions`

Key data can be tampered with using functions. Don't forget that functions are chainable: `{{ page.html | getHtmlById:"blog-post-content" | debug }}`.


#### Truncate

	truncate:[Number of characters allowed]

Strips all HTML, remove characters above the limit and appends `...` if necessary.

#### Truncate words

	truncatewords:[Number of words allowed]

Strips all HTML, remove words above the limit and appends `...` if necessary.

##### Example

	{{ keys.body | truncatewords:10 }}

#### Truncate words HTML

	truncatewordsHtml:[Number of words allowed]

Same as `truncatewords`, but doesn't strip HTML.

##### Example

	{{ keys.body | truncatewordsHtml:10 }}

#### HTML attribute

	attr:"[HTML attribute]"

Extract an HTML attribute.

##### Example

	{{ keys.image | attr:"src" }}

#### Format date

	format:"[Format string]"

Format a date (see Date format for syntax).

##### Example

	{{ page.publishDate | format:"%e %B %Y" }}

#### Resize image

	resize:[Width in pixels]x[Height in pixels], "[resize / crop]"

Resize an image. The first parameter can be either just width, height or both: `50`, `x50` or `50x50`. The second parameter specifies the method: `resize` scales the image, `crop` crops it.

##### Example

	{{ keys.image | resize:"50x50","crop" }}

#### Extract HTML element by ID

	getHtmlById:"[Html ID]"

Extract the inner HTML of an HTML element, by it's ID.

##### Example

	{{ page.html | getHtmlById:"blog-post-content" }}

#### Debug

	debug

Escape HTML entities for debugging purposes. Can also be used to show all available variables.

##### Example

	{{ page | debug }}

### `paginationHtml`

Uses Liquid syntax.

#### Variables

* `totalPages` - Total number of pages
* `pageNumber` - The current page
* `perPage` - How many items per page
* `count` - Total number of items
* `previous` - Object with url and page, if there is a previous page, otherwise set to null.
* `next` - Object with url and page, if there is a next page, otherwise set to null.


#### Filters

* `pageNumberToUrl` - Convert a page number to an URL.


#### Tags

* `paginate` - See *Another `paginationHtml` example* for example usage.


### Other parameters
* `htmlElement` - Defaults to `div`. What HTML element to wrap the `html` parameter with, i.e. every page. Additionally, this element will get any HTML attributes specified. HTML class `active` will automatically be set if the a HTML snippet links to the current URL.
* `perPage` - How many items to show per page. **If this is set, `paginationHtml` must also be set**.
* `limit` - Limit without pagination
* `offset` - Offset 1 if you don't want to show the first post.
* `childrenLevels` - How many levels of child pages
* `useChildPages` - Automatically use this page's child pages
* `createButton` - Creates a child page, to the page with the `com_keys`. This parameter sets the text on the button.
* `useRootParentChildPages` - Automatically use all this page's grandparent's children.
* `enablePageHtml` - Enable `{{ page.html }}`.


### Example with pagination

```
{ com_keys ( id:'2', description:'Keys', sortBy:'publishedDate descending', perPage:'2', paginationHtml:'
 
	{% if previous %}
		<a href="{{ previous.url }}">&larr; Go to page {{ previous.page }}</a>
	{% else %}
		[This is the first page]
	{% endif %}
 
	Page {{ pageNumber }} of {{ totalPages }}
 
	{% if next %}
		<a href="{{ next.url }}">Go to page {{ next.page }} &rarr;</a>
	{% else %}
		[This is the last page]
	{% endif %}
 
', html:'
 
	<pre>
 
Url: <a href="{{ page.url }}">{{ page.url }}</a>
 
{{ keys.heading }}
==================
 
{{ keys.body | truncatewords:5 }}
{{ keys.body | truncatewords:10 }}
{{ keys.body | truncatewords:20 }}
{{ keys.body }}
----------------------------------
 
	</pre>
 
' ) }
```


### Another `paginationHtml` example

```
{% if totalPages > 1 %}
<div id="pagination">
 
	<div class="pages">
		{% paginate page in pages current: pageNumber limit: 10 %}
			{% if page == pageNumber %}
				<span>{{ page }}</span>
			{% else %}
				<a href="{{ page | pageNumberToUrl }}">{{ page }}</a>
			{% endif %}
 
		{% endpaginate %}
	</div>
 
</div>
{% endif %}
```
