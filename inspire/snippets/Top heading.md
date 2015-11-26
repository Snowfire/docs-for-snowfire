#Top heading

### HTML

```html
<div class="top_heading">
	<div class="content">
		<div class="container intro">
			{ com_singlerow(
				id: '{{ component_id_1 }}',
				description: 'Headline',
				htmlElement:'h1's
			) }
			
			{ com_wysiwyg(
				id: '{{ component_id_2 }}',
				description: 'Subheading'
			) }
		</div>
	</div>
</div>

```
