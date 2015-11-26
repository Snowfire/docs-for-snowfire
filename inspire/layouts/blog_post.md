#Blogpost

###blog_post.tpl

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

    <div id="blog" class="snippet_area_main">
		<div class="container-fluid">
			<article>
				<div class="image max-height">
					{ com_image2(
						id: '102',
						description: 'Image',
						width: '1920',
						height: '500',
						description:'image',
						autoWidth:'true',
						dimensions:'min'
						key: 'image',
						html: '
							<div {{ attributes_html | html_decode }} style="background-image:url({{ src }})"></div>
						'
					) }
				</div>
				<div class="bg-fade"></div>

				<div class="container">
						<div class="col-md-10 col-md-offset-1">
							<div class="inner">
								{ com_singlerow(id: '100', description: 'Title', htmlElement: 'h1', value: '{ var_pageName }', key: 'title' ) }

								<div class="avatar">
									{ com_image2 (
										id:'110',
										description:'image',
										width: '110',
										height: '110',
										crop: 'true',
										dimensions:'max',
										key:'avatar'
									) }
								</div>

								<div class="text">
									{ com_singlerow(id: '101', description: 'Author', htmlElement:'span', class:'author', key:'author' ) }
									<span class="date">{ fnc_publishDate(format: '%e %B %Y') }</span>
								</div>
							</div>
						</div>
				</div>

			</article>
		</div>

		<div class="container">
				<div class="col-md-10 col-md-offset-1">
					<div class="blog-post">
						{ com_wysiwyg(id: '103', description: 'Enter text', enableLists: 'true', key: 'text') }
					</div>

					{{ snippet_area.main }}
				</div>
		</div>


		{ com_liquid2 ( id:'107', description:'Next article', code:'

		{% if page.previous %}
		<div class="next_article">


			<article class="posts">
				<div class="image">
					<div style="background-image:url({{ keys.image }})"></div>
				</div>
				<div class="overlay"></div>

				<div class="container">
						<div class="col-md-10 col-md-offset-1">

							<span class="tag">Nästa artikel</span>

							<div class="inner">

								<h2><a href="{{ page.previous.url }}">{{ page.previous.keys.title }}</a></h2>
								<div class="text">
									<span class="author">{{ page.previous.keys.author_text }}</span>

									<span class="date">{{ page.previous.publishDate | stringToDateFormat:"%B %e, %Y" }}</span>
								</div>
							</div>
						</div>
				</div>
			</article>


		</div>

		{% end_if %}
		' ) }

	</div>

</div>

```

###blog_post.xml

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

        <snippet id="wide_image_with_text"></snippet>
        <snippet id="statement"></snippet>
        <snippet id="top_heading"></snippet>
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