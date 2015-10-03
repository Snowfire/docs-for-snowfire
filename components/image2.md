Image2
=====

```xml
{ com_image2 (
  id:'{{ component_id }}', 
  description:'image', 
  autoWidth:'true', 
  dimensions:'max'
) }
```

Parameters
----------

* html
* width
* height
* autoWidth (boolean)
* dimensions
* placeholderWidth
* linkable (boolean)
* resizable (boolean)
* autoLinkToFile (boolean)


### html

Uses a Snowfire flavor of the Liquid template language.

Variables available are: 
* src
* attributes_html – e.g. `alt="" class="classes"`
* alt


### autoWidth

Automatically set width by parent element.


### dimensions

* `max` – Use width and height as max size
* `min` – Use width and height as min size


## Examples

### Use a `<div>` with a CSS background instead of an `img` tag

```
{ com_image2(
	id: '102',
	description: 'Image',
	width: '1920',
	height: '500',
	description:'image',
	autoWidth:'true',
	dimensions:'min'
	key: 'image',
	html: '
		<div {{ attributes_html | html_decode }} style="background-image:url({{ src }})"></div>
	'
) }
