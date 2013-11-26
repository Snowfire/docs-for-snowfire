Image
=====

```xml
{ com_image ( 
    id:          	'1', 
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

```
{% if link %}<a {{ a_parameters | html_decode }}>{% end_if %}
<img {{ img_parameters | html_decode }} />
{% if link %}</a>{% end_if %}
```
