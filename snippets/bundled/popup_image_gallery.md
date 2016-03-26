#Popup image gallery

### HTML

```html
<div class="popup-image-gallery">
	<div class="container">
		<div class="row">
            <div class="col-sm-4">
                { com_image2(
                    id: '{{ component_id_4 }}',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'min-max',
                    width: '360',
                    height: '240'
                ) }
            </div>

            <div class="col-sm-4">
                { com_image2(
                    id: '{{ component_id_5 }}',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'min-max',
                    width: '360',
                    height: '240'
                ) }
            </div>

            <div class="col-sm-4">
                { com_image2(
                    id: '{{ component_id_6 }}',
                    description: 'image',
                    autoLinkToFile: 'true',
                    resizable: 'false',
                    crop: 'true',
                    dimensions:'min-max',
                    width: '360',
                    height: '240'
                ) }
            </div>
		</div>
	</div>
</div>

```

###CSS
```css
.popup-image-gallery a {
	border-bottom: none;
}

.popup-image-gallery a:hover {
	text-decoration: none;
	border-bottom: none;
}

@media screen and (max-width: 768px) {
	.popup-image-gallery a img {
		margin-bottom: 15px;
	}
}

@media screen and (max-width: 700px) {
	.popup-image-gallery a img {
		width: 100%;
	}
}

.columns.popup-image-gallery + .columns.popup-image-gallery {
	margin-top: -35px;
}

.snippet_area_main > .two_popup-image-gallery .column.popup-image-gallery {
	width: 48.5%;
	margin-left: 3%;
}

.snippet_area_main > .two_popup-image-gallery .column:first-child.popup-image-gallery {
	margin-left: 0;
}

```



	