#Popup image gallery

### HTML

```html
	
<div class="popup-image-gallery">
	<div class="container">
		<div class="row">
	
            <div class="col-sm-4">
                { com_image2(
                    id: '500',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'max',
                    width: '360',
                    height: '240'
                ) }
            </div>
	
            <div class="col-sm-4">
                { com_image2(
                    id: '232',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'max',
                    width: '360',
                    height: '240'
                ) }
            </div>
	
            <div class="col-sm-4">
                { com_image2(
                    id: '123',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'max',
                    width: '360',
                    height: '240'
                ) }
            </div>
	
		</div>
	</div>
</div>

```


	