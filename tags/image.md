# Image

```html
<image2
    id="{{ component_id }}"
    description="Image"
    width="500"
    height="200"
    crop="true"
    resizable="false"
    dimensions="min-max"
></image2>
```

## Parameters

* `html`
* `width`
* `height`
* `auto-width` - (boolean)
* `dimensions`
* `placeholder-width`
* `crop` - (boolean) Set `resizable` to `false` when using this parameter
* `linkable` - (boolean)
* `resizable` - (boolean)
* `auto-link-to-file - (boolean)

### html

See how to use this in the examples below. Variables available are:

* `src`
* `attributes_html` – e.g. `alt="" class="classes"`
* `alt`
* `link`

### auto-width

Automatically set width by parent element.

### dimensions

* `min-max` – Use width and height as min size, resizes larger images to fit in the width height you have defined. _(Recommended)_
* `max` – Use width and height as max size.
* `min` – Use width and height as min size.

## Examples

### Use a `<div>` with a CSS background instead of an `<img>` tag

```
<image2
	id="{{ component_id }}"
	description="Image"
	width="1920"
	height="500"
	description="Image"
	auto-width="true"
	dimensions="min-max"
	key="image"
	html="
		{% if link %}<a href='{{ link }}'>{% end_if %}
			<div {{ attributes_html | html_decode }} style='background-image:url({{ src }})'></div>
		{% if link %}</a>{% end_if %}
	"
></image2>
```

### Crop image

This is great if you want to have multiple square images and maintain the aspect ratio between the images. This will force a larger image to be resized and cropped automatically. The user can change the crop, but it always maintains its aspect ratio (300x300, 1:1) in this example.

```
<image2
	id="{{ component_id }}"
	description="Image"
	width="300"
	height="300"
	dimensions="min-max"
	crop="true"
	resizable="false"
></image2>
```

### Usage on a blog summary page

If you have defined a key named `image` on your blog posts image2 component, this is how you show it in `com_keys`. Please note that you'll have to apply CSS classes to make sure your image div with the background has the size you want.

```html
{ com_keys (
	id:'{{ component_id }}',
	description:'Blog posts',
	html:'
		<article class="posts">
			<div class="image">
				<div style="background-image:url({{ keys.image | metaToImage: "crop", "200","200" }})"></div>
			</div>
			<a href="{{ page.url }}">{{ keys.title }}</a>
		</article>
	'
) }
```
