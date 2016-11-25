#Wide image with text

### HTML
```html
<div class="wide_image_with_text2">
	<div class="content">
	    <div class="intro">
	        { com_singlerow(
	            id: '{{ component_id_1 }}',
	            description: 'Headline',
	            htmlElement:'h1'
	        ) }
	
	        { com_wysiwyg(
	            id: '{{ component_id_2 }}',
	            description: 'Subheading'
	        ) }
	
	        <span class="sf-button">
	            { com_link(
	                id: '{{ component_id_3 }}',
	                description: 'Button'
	            ) }
	        </span>
	    </div>
	</div>
	
	{ com_image2 (
	    id: '{{ component_id_0 }}',
	    description: 'Image',
	    width: '1920',
	    height: '615',
	    dimensions: 'min',
	    resizable: 'false',
	    html: '
	        <div class="wide_image">
	            <div {{ attributes_html | html_decode }} style="height:410px;background-image:url({{ src }})">
	                <div class="overlay"></div>
	            </div>
	        </div>
	    '
	  )
	}
</div>

```
