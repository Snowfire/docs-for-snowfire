# Simple blog

#### `simple_blog.tpl`

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

	<div class="color_block">
        <div class="content one">
            { com_wysiwyg(
                id: '196',
                description: 'Subheading',
                customBlockformats: 'Quote|blockquote', 
                enableLists: 'true',
                attachImage:'true',
                class: 'text'
            ) }
        </div>
    </div>

    <div class="container">
        <div id="simple-blog" class="simple-blog">

            { com_keys (
                id:'197',
                description:'Blog posts',
                class:'post',
                createButton: 'New post',
                enablePageHtml: 'true',
                html:'

                     {{ page.html| getHtmlById:"simple-blog" }}

                ',
                sortBy:'publishedDate descending',
                useChildPages: 'true',
                perPage: '25',
                offset: '0',
                paginationHtml:'
                    <div class="row">
                        {% if totalPages > 1 %}
                            <div class="col-md-12">
                                <nav class="text-center">
                                    <ul class="pagination">

                                        {% paginate page in pages current: pageNumber limit: 10 %}
                                      
                                        {% if page == pageNumber %}
                                            <li class="active"><a href="{{ page | pageNumberToUrl }}">{{ page }}</a></li>
                                            {% else %}
                                            <li><a href="{{ page | pageNumberToUrl }}">{{ page.number }}</a></li>
                                        {% endif %}

                                        {% endpaginate %}

                                    </ul>
                                </nav>
                            </div>
                        {% endif %}
                    </div> 
                '
            ) }

        </div>
    </div>

    {{ partial: footer.tpl }}

</div>
```

#### `simple_blog.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
    </options>

    <template_config>
        <settings>
            <children>
                <layouts allowNewLayout="true" snippetContainer="simple_blog_post" />
                <contentType>post</contentType>
                <noAddToMenu>true</noAddToMenu>
                <notEmpty>true</notEmpty>
            </children>
        </settings>
        <childrenRss>
            <item>
                <content type="html-id">article</content>
            </item>
        </childrenRss>
    </template_config>

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

###CSS

```css

#simple-blog article {
	max-width: 730px;
	margin: 0 auto;
	position: relative;
	margin-top: 100px;
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	#simple-blog article {
		margin-bottom: 30px;
	}
}

#simple-blog article:first-child {
	margin-top: 50px;
}

@media screen and (max-width: 768px) {
	#simple-blog article:first-child {
		margin-top: 20px;
	}
}

#simple-blog article p {
	position: relative;
}

#simple-blog article h2 {
	margin-bottom: 0;
}

#simple-blog article small {
	margin-bottom: 15px;
	margin-top: -3px;
	display: block;
}

#simple-blog article small h5 {
	display: inline-block;
}

#simple-blog article .main_image {
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	#simple-blog article .main_image {
		margin-bottom: 30px;
	}
}

#simple-blog article .left-fig {
	float: left;
	margin-left: 0%;
	padding-right: 10px;
}

@media only screen and (min-width: 992px) {
	#simple-blog article .left-fig {
		float: left;
		margin-left: -20%;
		padding-right: 10px;
	}
}

#simple-blog article figcaption {
	font-size: 13px;
	padding-top: 5px;
}

#simple-blog .snippet_area {
	margin-left: auto;
	margin-right: auto;
	max-width: 730px;
}

#simple-blog.one-post article {
	margin-top: 20px;
}

@media screen and (max-width: 768px) {
	#simple-blog.one-post article {
		margin-top: -20px;
	}
}

#simple-blog .post:after {
	height: 4px;
	width: 40px;
	content: '';
	left: 0;
	right: 0;
	margin-left: auto;
	margin-right: auto;
	margin-bottom: 100px;
	margin-top: 100px;
	display: block;
	opacity: 0.4;
}

@media screen and (max-width: 768px) {
	#simple-blog .post:after {
		margin-bottom: 60px;
		margin-top: 60px;
	}
}

#simple-blog .post.last:after {
	display: none;
}

#simple-blog #pagination {
	margin-top: -1.6em;
	margin-bottom: 2em;
}

#simple-blog #pagination .pages {
	text-align: center;
}

#simple-blog #pagination .pages a:hover {
	text-decoration: underline;
}

#simple-blog #pagination .pages a, #simple-blog #pagination .pages span {
	display: inline-block;
	padding: 5px 10px;
}

#simple-blog #pagination .pages span {
	font-weight: bold;
}

.top-menu-wrapper + .appear_as_top_heading_block {
	margin-top: -60px;
}

@media screen and (max-width: 768px) {
	.top-menu-wrapper + .appear_as_top_heading_block {
		margin-top: -30px;
	}
}

@media screen and (max-width: 768px) {
	.blog-posts + footer {
		margin-top: 15px;
	}
}

```