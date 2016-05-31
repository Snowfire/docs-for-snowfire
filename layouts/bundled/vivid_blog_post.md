# Vivid blog post

#### `vivid_blog_post.tpl`

```html
{{ partial: top.tpl }}

<div class="vivid-blog-post-wrapper">
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

					        <h5>{ fnc_publishDate(format: '%e %B %Y') }</h5>

                            <span class="dot-divider"></span>

                            <a class="share-icon share-icon-fb fa fa-facebook" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
                            <a class="share-icon share-icon-twitter fa fa-twitter" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
                            <a class="share-icon share-icon-linkedin fa fa-linkedin" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
				        </small>
			        </header>

					<main class="vivid-blog-content">
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
		        	</main>
			
				    {{ snippet_area.main }}

                    <div class="vivid-post-footer">
                        <div class="row">
                            <div class="col-md-6">
                                <div class="vivid-post-tags">
                                    { com_liquid2 (
                                        id:'105', 
                                        description:'Tags will be displayed here',
	                                    selectablePage:'false',
                                        code:'
                                            <ul>
                                            {% for page.tags as tag %}
                                                <li><a href="{{ tag | tagToUrl:page }}">{{ tag }}</a></li>
                                            {% end_for %}
                                            </ul>
                                        ')
                                    }
                                </div>
                            </div>
                            <div class="col-md-6">
                                <div class="vivid-post-share">
                                    <p class="label-style share-title">Share this:</p>

                                    <a class="share-icon share-icon-fb fa fa-facebook" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
                                    <a class="share-icon share-icon-twitter fa fa-twitter" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
                                    <a class="share-icon share-icon-linkedin fa fa-linkedin" data-shareurl="{ var_url }" data-sharetitle="{ var_pageName }" href="javascript:;"></a>
                                </div>
                            </div>
                        </div>
                    </div>

                    {{ snippet_area.comments }}

			    </div>
			</div>

			<div class="col-md-3">
				<div class="vivid-sidemenu-latest-posts">
					[% set parent = currentParent() %]

					<ul>
						[% for tag in siblingTags('limit: 10', 'pageLimit: 5') %]
							<li>
								<a href="[[ parent.page.url ]]/[[ tag.name | url('tag') ]]">
                                    <h4>[[ tag.name ]]</h4>
                                </a>

								<ul class="latest-posts">
									[% for page in tag.pages %]
									<li>
										<a href="[[ page.id | url('page') ]]">[[ page.name ]]</a>
									</li>
									[% endfor %]
								</ul>
							</li>
						[% endfor %]
					</ul>
				</div>
			</div>
			
	    </div>
    </div>

    <div class="vivid-post-navigate">
        <div class="container">
            <div class="inner text-center">
                { com_liquid2 ( 
                    id:'220', 
                    description:'Previous and next post', 
                    code:'
                        {% if page.next %}
                            <a href="{{ page.next.url }}" class="icon prev-arrow"><i class="fa fa-angle-left"></i></a>
                        {% end_if %}
                    
                        <a href="{{ parent.url }}" class="label-style">View all</a>
                    
                        {% if page.previous %}
                            <a href="{{ page.previous.url }}" class="icon next-arrow"><i class="fa fa-angle-right"></i></a>
                        {% end_if %}
                    ' 
                ) }
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
        <template_engine>active</template_engine>
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

    <snippets area="comments" width="1130" column_spacing="2%" add_button="Add comments" all_user_snippets="true">
        <snippet id="facebook_comments" />
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