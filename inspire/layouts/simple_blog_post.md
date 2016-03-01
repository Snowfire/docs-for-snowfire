# Simple blog post

#### `simple_blog_post.tpl`

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

    <div id="simple-blog" class="snippet_area_main">

	    <article>
	        <header>
				<a href="{ var_pageFullUrl }">{ com_singlerow(id: '195', description: 'Title', htmlElement: 'h2', value: '{ var_pageName }', key: 'title' ) }</a>
		        <small>
			        { com_singlerow(id: '194', description: 'Author', htmlElement:'span', class:'author', key:'author' ) }
			        <span class="date">{ fnc_publishDate(format: '%e %B %Y') }</span>
		        </small>
	        </header>
		    <div class="main_image">
		        { com_image2(
		            id: '196',
		            description: 'Image',
		            width: '650',
		            height: '300',
					resizable: 'false',
		            crop: 'true',
		            key: 'image'
		        ) }
		    </div>

	        { com_wysiwyg(id: '193', description: 'Enter text', enableLists: 'true', key: 'text') }

        </article>

	    {{ snippet_area.main }}

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
        <snippet id="image2" />
        <snippet id="video" />
        <snippet id="form" />
        <snippet id="map" />
        <snippet id="html" />
        <snippet id="latest_posts" />
        <snippet id="quote2" />
        <snippet id="facebook" />
        <snippet id="facebook_comments" />
        <snippet id="divider" />
        <snippet id="sociallinks" />
        <snippet id="product" />
        <snippet id="cta_button" />

    </snippets>

    <snippets area="footer" width="1160" column_spacing="2%" sync="true">
        <snippet id="slider_synced" />
        <snippet id="text_synced" />
        <snippet id="image2_synced" />
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
        <snippet id="cta_button_synced" />
    </snippets>


</snippet_container>
```
