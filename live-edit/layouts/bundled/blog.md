# Blog

#### `blog.tpl`

```html
{{ partial: top.tpl }}

<div class="blog-posts">

    <div class="container">

            { com_keys (
                id:'100',
                description:'Blog posts',
                class:'post',
                createButton: 'New post',
                html:'
                    <article class="wide-blog-image">
                        <div class="image">
                            <div style="background-image:url({{ keys.image | metaToImage }})"></div>
                        </div>
                        <div class="bg-fade"></div>
                        <div class="col-md-10 col-md-offset-1 relative">
                            <div class="inner">
                                <a href="{{ page.url }}" class="act-as-h1">{{ keys.title }}</a>

                                {% if keys.avatar %}
                                <div class="avatar">
                                    <div class="avatar-img" style="background-image:url({{ keys.avatar | metaToImage }})"></div>
                                </div>
                                {% endif %}

                                <div class="text">
                                    {% if keys.author %}
                                    <span class="author label-style">{{ keys.author }}</span>
                                    {% endif %}
                                    <span class="date label-style">{{ page.publishDate | format:"%e %B %Y" }}</span>
                                </div>
                            </div>
                        </div>
                    </article>
                ',
                sortBy:'publishedDate descending',
                useChildPages: 'true',
                perPage: '10',
                offset: '0',
                paginationHtml:'
                {% if totalPages > 1 %}
                    <div id="pagination">

                        <div class="pages">
                            {% paginate page in pages current: pageNumber limit: 20 %}
                            {% if page == pageNumber %}
                            <span class="page">{{ page }}</span>
                            {% else %}
                            <a href="{{ page | pageNumberToUrl }}" class="page">{{ page }}</a>
                            {% endif %}

                            {% endpaginate %}
                        </div>
                    </div>
                {% endif %}
                '
            ) }


    </div>
</div>

{{ partial: footer.tpl }}


```

### `blog.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
    </options>

    <template_config>
        <settings>
            <children>
                <layouts allowNewLayout="true" snippetContainer="blog_post" />
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
This styles blog overview and blog post. 

```
.wide-blog-image {
	position: relative;
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	.wide-blog-image {
		height: 300px;
		margin-bottom: 30px;
	}
}

.wide-blog-image .image div {
	height: 500px;
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center center;
}

@media screen and (max-width: 768px) {
	.wide-blog-image .image div {
		height: 300px;
	}
}

.wide-blog-image .bg-fade {
	position: absolute;
	top: 0;
	left: 0;
	right: 0;
	bottom: 0;
	pointer-events: none;
	background: url("/themes/inspire/public/images/fade.png") repeat-x bottom center;
	opacity: 0.8;
}

.wide-blog-image .overlay {
	background-color: rgba(66, 66, 66, 0.6);
	position: absolute;
	left: 0;
	right: 0;
	bottom: 0;
	height: 500px;
}

@media screen and (max-width: 768px) {
	.wide-blog-image .overlay {
		height: 300px;
	}
}

.wide-blog-image .inner {
	position: absolute;
	bottom: 80px;
}

@media screen and (max-width: 992px) {
	.wide-blog-image .inner {
		bottom: 40px;
	}
}

.wide-blog-image a,
.wide-blog-image h1 {
	color: #fff;
	display: block;
	margin-bottom: 10px;
}

@media screen and (max-width: 768px) {
	.wide-blog-image a,
	.wide-blog-image h1 {
		font-size: 30px;
	}
}

.wide-blog-image .avatar {
	float: left;
	margin-right: 25px;
}

.wide-blog-image .avatar img,
.wide-blog-image .avatar .avatar-img {
	border-radius: 100%;
	width: 55px;
	height: 55px;
	background-size: cover;
}

@media screen and (max-width: 768px) {
	.wide-blog-image .avatar img,
	.wide-blog-image .avatar .avatar-img {
		width: 35px;
		height: 35px;
	}
}

.wide-blog-image .text {
	float: left;
	margin-top: 10px;
}

@media screen and (max-width: 768px) {
	.wide-blog-image .text {
		margin-top: 1px;
	}
}

.wide-blog-image .text .date,
.wide-blog-image .text .author {
	display: block;
	color: #fff;
}

.wide-blog-image.next-article {
	margin-bottom: 0;
}

.wide-blog-image .tag {
	display: block;
	position: absolute;
	bottom: 439px;
	color: #fff;
	font-weight: 400;
	padding: 20px;
	text-transform: uppercase;
	letter-spacing: 0.09em;
	font-size: 16px;
}

@media screen and (max-width: 768px) {
	.wide-blog-image .tag {
		bottom: 239px;
	}
}

.blog-post-intro {
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	.blog-post-intro {
		margin-bottom: 30px;
	}
}

.blog .snippet_area {
	margin-left: auto;
	margin-right: auto;
	max-width: 730px;
}

#pagination .pages {
	margin-top: 50px;
	width: 100%;
	font-size: 17px;
	letter-spacing: 0.09em;
	font-weight: 200;
	text-transform: uppercase;
	padding: 10px;
}

#pagination .pages a {
	text-decoration: underline;
}

.top-menu-wrapper + .blog > .wide-blog-image:first-child {
	margin-top: -60px;
}

@media screen and (max-width: 768px) {
	.top-menu-wrapper + .blog > .wide-blog-image:first-child {
		margin-top: -30px;
	}
}

```