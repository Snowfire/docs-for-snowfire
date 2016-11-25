#Photo collage

This block contains four images in a row with text on hover.

###HTML
``` HTML
<section class="photo-collage">
	<div class="container-fluid">
		<div class="row">
			
			<div class="col-sm-3 col-xs-6 photo">
				<div class="overlay">
					<div class="overlay-content">
						{ com_singlerow (
							id: '{{ component_id_1 }}',
							description: 'Enter text',
							class: 'name',
							htmlElement: 'span'
						) }
							
					</div>
				</div>
				
				{ com_image2 (
					  id: '{{ component_id_2 }}',
					  description:'image',
					  dimensions:'min-max',
					  width: '350',
					  height: '350',
					  crop: 'true'
				) }
			</div>
			
			<div class="col-sm-3 col-xs-6 photo">
				<div class="overlay">
					<div class="overlay-content">
						{ com_singlerow (
							id: '{{ component_id_3 }}',
							description: 'Enter text',
							class: 'name',
							htmlElement: 'span'
						) }
						
					</div>
				</div>
				
				{ com_image2 (
					  id: '{{ component_id_4 }}',
					  description:'image',
					  dimensions:'min-max',
					  width: '350',
					  height: '350',
					  crop: 'true'
				) }
			</div>
			
			<div class="col-sm-3 col-xs-6 photo">
				<div class="overlay">
					<div class="overlay-content">
						{ com_singlerow (
							id: '{{ component_id_5 }}',
							description: 'Enter text',
							class: 'name',
							htmlElement: 'span'
						) }
						
					</div>
				</div>
				
				{ com_image2 (
					  id: '{{ component_id_6 }}',
					  description:'image',
					  dimensions:'min-max',
					  width: '350',
					  height: '350',
					  crop: 'true'
				) }
			</div>
			
			<div class="col-sm-3 col-xs-6 photo">
				<div class="overlay">
					<div class="overlay-content">
						<div class="startup-logo univrses"></div>
						
						{ com_singlerow (
							id: '{{ component_id_7 }}',
							description: 'Enter text',
							class: 'name',
							htmlElement: 'span'
						) }
						
					</div>
				</div>
				
				{ com_image2 (
					  id: '{{ component_id_8 }}',
					  description:'image',
					  dimensions:'min-max',
					  width: '350',
					  height: '350',
					  crop: 'true'
				) }
			</div>
		</div>
	</div>
</section>
```

###CSS
```css
.photo-collage .photo {
	position: relative;
	padding: 0;
}

.photo img {
	width: 100%;
}

.photo-collage .photo .overlay {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0,0,0, 0.55);
	transition: all 0.3s ease-in-out;
	pointer-events: none;
	    
	opacity: 0;
}

.photo-collage .photo:hover .overlay { 
	opacity: 1;
}

.photo-collage .photo .overlay-content {
	padding: 10px;
	text-align: center;
	pointer-events: auto;
	cursor: pointer;
	    
	position: absolute;
	top: 50px;
	left: 0;
	right: 0;
}

.overlay-content .name {
	color: #fff;
	text-align: center;
	display: block;
	letter-spacing: 0.5px;
}
```

