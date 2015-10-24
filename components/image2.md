Image2
=====

```xml
{ com_image2 (
  id:'{{ component_id }}', 
  description:'image', 
  width:'500',
  height:'500',
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
* crop (boolean) - Set `resizable` to `false` when using this parameter
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
```

### Crop image

This is great if you want to have multiple square images and maintain the aspect ratio between the images. This will force a larger image to be resized and cropped automatically. The user can change the crop, but it always maintains its aspect ratio (300x300, 1:1) in this example.

```
{ com_image2 (
	id: '{{ component_id }}', 
	description: 'image',  
	width: '300',
	height: '300',
	dimensions: 'max',
	crop: 'true',
	resizable: 'false'
) }
```

### Usage on a blog summary page

If you have defined a key named `image` on your blog posts image2 component, this is how you show it in `com_keys`. Please note that you'll have to apply CSS classes to make sure your image div with the background has the size you want.


```html
{ com_keys (
	id:'100',
	description:'Blog posts',
	html:'
		<article class="posts">
			<div class="image">
				<div style="background-image:url({{ keys.image | metaToImage }})"></div>
			</div>
			<a href="{{ page.url }}">{{ keys.title }}</a>
		</article>
	'
) }
```
