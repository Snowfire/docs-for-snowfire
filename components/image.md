Image
=====

```xml
{ com_image ( 
    id:          	'{{ component_id }}', 
    description: 	'Image', 
    maxHeight:   	'300',
    linkable:    	'true'
) }
```

Parameters
----------

* maxWidth
* maxHeight
* linkable - boolean.
* crop - boolean.
* altAsLinkTitle - boolean.
* linkClass - class on `<a>` tag. Deprecated, use parameter `a-class` instead.
* canHaveEmptyLink - By default the `<a>` tag is stripped out if no link was selected by the user.
* enableVideo - boolean.
* autoLinkToFile - boolean. Will automatically link the image to the original image file. _Requires linkable:'true'_
* placeholderHeight - Specific width/height for the place holder image
* placeholderWidth - Specific width/height for the place holder image
* html - what the output will look like. See below.

### `html`

Uses a Snowfire flavor of the Liquid template language.
Variables available are `src`, `alt`, `link`, `a_parameters` and `img_parameters`.  

#### Default value

```html
{% if link %}<a {{ a_parameters | html_decode }}>{% end_if %}
<img {{ img_parameters | html_decode }} />
{% if link %}</a>{% end_if %}
```

Examples
--------

### Default settings

```html
{ com_image ( 
	id:'{{ component_id }}', 
	description:'image', 
	maxWidth:'{{ column_width }}', 
	linkable:'true' 
) }
```


### Use a `<div>` with a CSS background instead of an `img` tag

```html
{ com_image(
	id:             '1',
	description:    'Add image',
	maxHeight:      '260',
	maxWidth:       '1920',
	html: '
		<div {{ img_parameters | html_decode }} style="background-image:url({{ src }})"></div>
	'
) }
```
