# Vivid blog post

#### `vivid_blog_post.tpl`

```html
{{ partial: top.tpl }}

<div class="vivid-blog-wrapper vivid-blog">
    <div class="container">
    	<div class="row">
			<div class="col-md-9">
				<div class="vivid-blog-post">
			        <header class="vivid-blog-top">
						<a href="{ var_pageFullUrl }">
							{ com_singlerow(
								id: '195', 
								description: 'Title', 
								htmlElement: 'h2', 
								value: '{ var_pageName }', 
								key: 'title'
							) }
						</a>
				        <small>
					        { com_singlerow(
					        	id: '194',
					        	description: 'Author',
					        	htmlElement: 'h5', 
					        	class: 'author'
				        	) }
                            <span class="dot-divider">·</span>
					        <h5>{ fnc_publishDate(format: '%e %B %Y') }</h5>
				        </small>
			        </header>

					<div class="vivid-blog-content">
					    <div class="main_image">
					        { com_image2(
					            id: '196',
					            description: 'Image',
					            width: '850',
								resizable: 'false',
								dimensions: 'min-max',
					            key: 'image'
					        ) }
					    </div>
			
                        <div class="one">
    				        { com_wysiwyg(
    				        	id: '193',
    				        	description: 'Enter text', 
    				        	enableLists: 'true',
                                class: 'text',
    				        	key: 'text'
    			        	) }
                        </div>
		        	</div>
			
				    {{ snippet_area.main }}
			    </div>
			</div>
			<div class="col-md-3">
				<!-- <div class="vivid-sidemenu">
                    { com_singlerow(
                        id: '198',
                        syncId: '198',
                        description: 'Title',
                        htmlElement: 'p',
                        class: 'label-style'
                    )}
                    
                    { com_liquid2 (
                        id:'199', 
                        description: 'Tags', 
                        selectablePage: 'false', 
                        siblingTags: 'true',
                        code:'
                        <ul>
                            {% for siblingTags as tag %}
                                <li>
                                    <a href="{{ tag | tagToUrl:page }}">{{ tag }}</a>
                                </li>
                            {% end_for %}
                         </ul>
                    ') }
				</div> -->
			</div>
			
	    </div>
    </div>
</div>

{{ partial: footer.tpl }}
```

#### `vivid_blog_post.xml`

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
        <snippet id="text_synced" />
        <snippet id="video_synced" />
        <snippet id="form_synced" />
        <snippet id="map_synced" />
        <snippet id="slider_synced" />
        <snippet id="latest_posts_synced" />
        <snippet id="quote2_synced" />
        <snippet id="facebook_synced" />
        <snippet id="facebook_comments" />
        <snippet id="sociallinks_synced" />
        <snippet id="product_synced" />
        <snippet id="sf_btn_synced" />
        <snippet id="wide_image_synced" />
        <snippet id="html_synced" />
    </snippets>
    
</snippet_container>
```