#Color block

### HTML

```html
	
<div class="color_block">
	<div class="content one">
        { com_wysiwyg(
            id: '{{ component_id_1 }}',
            description: 'Subheading',
            customBlockformats: 'Quote|blockquote', 
            enableLists: 'true',
            attachImage:'true',
            class: 'text'
        ) }
    </div>
</div>

```
###CSS

```css
.color_block .content {
	padding-top: 60px;
	padding-bottom: 60px;
}

.color_block .content p {
	font-size: 16px;
	font-weight: 400;
	max-width: 730px;
	width: 100%;
	margin-left: auto;
	margin-right: auto;
}

.color_block .content p:last-child {
	margin-bottom: 0;
}

```

	