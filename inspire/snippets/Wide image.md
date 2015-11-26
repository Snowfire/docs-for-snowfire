#Wide image

### HTML

```html
<div class="wide_image">
	{ com_image2 (
	    id: '{{ component_id_0 }}',
	    description: 'Image',
	    width: '1920',
	    height: '350',
	    dimensions: 'min',
	    resizable: 'false',
	    html: '
	        <div class="wide_image">
	            <div {{ attributes_html | html_decode }} style="height:350px;background-image:url({{ src }})">
	                <div class="overlay"></div>
	            </div>
	        </div>
	    '
	  )
	}
</div>

```
