# Image collection

Great to use for sliders or image galleries. 


## Parameters

* itemHtml (required)
* htmlElement
* width
* height
* crop
* placeholderHeight
* autodetectWidth


### `itemHtml`

Variables:

* `%image%` – HTML code for image with link if set.


## Slider example using Flexslider

```html
<div class="flexslider">
	{ com_imagecollection (
		id: '{{ component_id }}',
		description: 'Add image',
		htmlElement: 'ul',
		class: 'slides',
		width: '{{ column_width }}',
		autodetectWidth:'true',
		height: '400',
		crop: 'true',
		itemHtml: '
			<li>%image%</li>
		'
	) }
</div>
```
