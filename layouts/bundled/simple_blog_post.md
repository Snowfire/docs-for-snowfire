# Simple blog post

#### `simple_blog_post.tpl`

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

    <div class="container">
	    <div id="simple-blog" class="simple-blog one-post">

		    <article>
		        <header>
					<a href="{ var_pageFullUrl }">{ com_singlerow(id: '195', description: 'Title', htmlElement: 'h2', value: '{ var_pageName }', key: 'title' ) }</a>
			        <small>
				        { com_singlerow(
				        	id: '194', 
				        	description: 'Author', 
				        	htmlElement: 'h5',
				        	key: 'author' 
			        	) }
			        	<span class="dot-divider">·</span>
				        <h5>{ fnc_publishDate(format: '%e %B %Y') }</h5>
			        </small>
		        </header>
			    <div class="main_image">
			        { com_image2(
			            id: '196',
			            description: 'Image',
			            width: '830',
						resizable: 'false',
						dimensions: 'min-max',
			            key: 'image'
			        ) }
			    </div>

		        { com_wysiwyg(id: '193', description: 'Enter text', enableLists: 'true', key: 'text') }

	        </article>

		    	{{ snippet_area.main }}


	    </div>
    </div>

    {{ partial: footer.tpl }}

</div>

```


#### `simple_blog_post.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
    </options>

    <snippets area="main" width="1130" column_spacing="2%" all_user_snippets="true">
        <snippet id="slider" />
        <snippet id="text" />
        <snippet id="video" />
        <snippet id="form" />
        <snippet id="map" />
        <snippet id="html" />
        <snippet id="latest_posts" />
        <snippet id="quote2" />
        <snippet id="facebook" />
        <snippet id="facebook_comments" />
        <snippet id="sociallinks" />
        <snippet id="product" />
        <snippet id="sf_btn" />
        <snippet id="color_block" />
    </snippets>

    <snippets area="footer" width="1160" column_spacing="2%" sync="true">
        <snippet id="slider_synced" />
        <snippet id="text_synced" />
        <snippet id="video_synced" />
        <snippet id="form_synced" />
        <snippet id="map_synced" />
        <snippet id="html_synced" />
        <snippet id="latest_posts_synced" />
        <snippet id="quote2_synced" />
        <snippet id="facebook_synced" />
        <snippet id="facebook_comments" />
        <snippet id="divider" />
        <snippet id="sociallinks_synced" />
        <snippet id="product_synced" />
        <snippet id="sf_btn_synced" />
    </snippets>

</snippet_container>
```

