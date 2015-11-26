#Product collection

### HTML

```html

<div class="product-collection">
	<div class="container">
		<div class="row">
			<div class="col-sm-3">
			{ com_product ( id:'500', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-sm" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"395x395", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
	                        <div class="price">
	                            {% if cart.display_price_with_vat %}
	                                {{ product.price_with_vat | money }}
	                            {% else %}
	                                {{ product.price | money }}
	                            {% end_if %}
	                        </div>
	                    </div>
					</article>
				</a>
			' ) }
			</div>
	
			<div class="col-sm-3">
			{ com_product ( id:'501', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-sm" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"395x395", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
							<div class="price">
	
								{% if cart.display_price_with_vat %}
									{{ product.price_with_vat | money }}
								{% else %}
									{{ product.price | money }}
								{% end_if %}
							</div>
						</div>
					</article>
				</a>
			' ) }
			</div>
	
			<div class="col-sm-6">
			{ com_product ( id:'502', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-sm" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"600x600", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
							<div class="price">
	
								{% if cart.display_price_with_vat %}
									{{ product.price_with_vat | money }}
								{% else %}
									{{ product.price | money }}
								{% end_if %}
							</div>
						</div>
					</article>
				</a>
			' ) }
			</div>
	
			<!-- Next row -->
			<div class="col-sm-6">
			{ com_product ( id:'503', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-lg  margin-top" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"600x600", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
							<div class="price">
	
								{% if cart.display_price_with_vat %}
									{{ product.price_with_vat | money }}
								{% else %}
									{{ product.price | money }}
								{% end_if %}
							</div>
						</div>
					</article>
				</a>
			' ) }
			</div>
	
			<div class="col-sm-3">
			{ com_product ( id:'504', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-sm" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"395x395", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
							<div class="price">
	
								{% if cart.display_price_with_vat %}
									{{ product.price_with_vat | money }}
								{% else %}
									{{ product.price | money }}
								{% end_if %}
							</div>
						</div>
					</article>
				</a>
			' ) }
			</div>
	
			<div class="col-sm-3">
			{ com_product ( id:'505', description:'Product', html: '
				<a href="{{ product.url }}">
					<article class="collection-product-sm" data-product-id="{{ product.id }}">
						<span class="image">
							<img src="{{ product.primary_image_src | resize:"395x395", "crop", "fill" }}" alt="" />
						</span>
	
						<div class="product-content">
							<h3 class="name">{{ product.name }}</h3>
							<div class="price">
	
								{% if cart.display_price_with_vat %}
									{{ product.price_with_vat | money }}
								{% else %}
									{{ product.price | money }}
								{% end_if %}
							</div>
						</div>
					</article>
				</a>
			' ) }
			</div>
	    </div>
	</div>
</div>

```


