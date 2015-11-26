#Product

### HTML

```html
{ com_product ( id:'234', description:'Product', html: '
	<article class="product sf-product" data-product-id="{{ product.id }}">
		<span class="image">
			<img src="{{ product.primary_image_src | resize:"395x395", "crop", "fill" }}" alt="" />
		</span>
		
		<span class="name">{{ product.name }}</span>
		
		<span class="price">
			{% if cart.display_price_with_vat %}
				{{ product.price_with_vat | money }}
			{% else %}
				{{ product.price | money }}
			{% end_if %}
		</span>
		
		<span class="overlay"></span>
		
		<span class="actions">
			<a href="{{ product.url }}">{{ "View product" | translate }}</a>
		</span>
	</article>
' ) }

```


	