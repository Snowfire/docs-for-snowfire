### blog_post.tpl

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

    <div id="blog" class="snippet_area_main">

	    <article>
	        <header>
		        { com_singlerow(id: '100', description: 'Title', htmlElement: 'h1', value: '{ var_pageName }', key: 'title' ) }
		        <small>
			        { com_singlerow(id: '101', description: 'Author', htmlElement:'span', class:'author', key:'author' ) }
			        <span class="date">{ fnc_publishDate(format: '%e %B %Y') }</span>
		        </small>
	        </header>
		    <div class="main_image">
		        { com_image(
		            id: '102',
		            description: 'Image',
		            maxWidth: '650',
		            maxHeight: '300',
		            crop: 'true',
		            key: 'image'
		        ) }
		    </div>

	        { com_wysiwyg(id: '103', description: 'Enter text', enableLists: 'true', key: 'text') }

        </article>

	    {{ snippet_area.main }}

    </div>

    {{ partial: footer.tpl }}

</div>
```