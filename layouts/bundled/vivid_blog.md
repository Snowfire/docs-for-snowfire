# Vivid blog

#### `vivid_blog.tpl`

```html
<div class="vivid-blog-posts">

    {{ partial: top.tpl }}

    <div class="vivid-blog-wrapper">
        <section class="container">
            <div class="row">
                <div class="col-md-9">
                    
                    <div class="row">

                        { com_keys (
                            id:'197',
                            description:'Blog posts',
                            class:'col-sm-6 col-md-4 vivid-post',
                            createButton: 'New post',
                            enablePageHtml: 'true',
                            html:'
                                <a href="{{ page.url }}">
                                    <div class="vivid-entry">
                                        <div class="vivid-entry-img">
                                            {% if keys.image %}
                                                <div style="background-image:url({{ keys.image | metaToImage }})"></div>
                                            {% endif %}
                                        </div>
                                        <div class="vivid-entry-info">
                                            <h3>{{ keys.title }}</h3>
                                            <p>{{ keys.text | limitWords: 10 }}</p>
                                            <h5 class="date">{{ page.publishDate | format:"%e %B %Y" }}</h5>
                                        </div>
                                    </div>
                                </a>
                            ',
                            sortBy:'publishedDate descending',
                            useChildPages: 'true',
                            perPage: '9',
                            offset: '0',
                            paginationHtml:'
                            <div class="clearfix"></div>
                            {% if totalPages > 1 %}
                                    <nav class="text-center">
                                        <ul class="pagination">
                                            {% paginate page in pages current: pageNumber limit: 10 %}
                                                {% if page == pageNumber %}
                                                <li class="active"><a href="{{ page | pageNumberToUrl }}">{{ page }}</a></li>
                                                {% else %}
                                                <li><a href="{{ page | pageNumberToUrl }}">{{ page }}</a></li>
                                                {% endif %}
                                            {% endpaginate %}

                                        </ul>
                                    </nav>
                            {% endif %}
                            '
                        ) }
                    </div>
                </div>
                
                <div class="col-md-3">
                    <div class="vivid-sidemenu-latest-posts">
                        <ul>
                            [% set current = current() %]

                            [% set tags = childrenTags('limit: 10', 'pageLimit: 5') %]

                            [% if tags == false %]
                                [[ "Group your posts with tags. They will show up here" | retell | onlyInLiveEdit ]]
                            [% endif %]

                            [% for tag in tags %]

                                [% if current.tag.id == tag.id %]
                                    <li class="active">
                                [% else %]
                                    <li>
                                [% endif %]

                                        <a href="[[ current.page.url ]]/[[ tag.name | url('tag') ]]"    >
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
        </section>
    </div>

    {{ partial: footer.tpl }}

</div>
```

### `vivid_blog.xml`

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet_container>

    <options>
        <component_id_offset>1000</component_id_offset>
        <template_engine>active</template_engine>
    </options>

    <template_config>
        <settings>
            <children>
                <layouts allowNewLayout="true" snippetContainer="vivid_blog_post" />
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
This styles both vivid blog overview and vivid blog post. 

```
.vivid-blog-wrapper {
	width: 100%;
	position: relative;
	background-color: #F5F5F5;
	padding-top: 30px;
	padding-bottom: 50px;
}

@media screen and (min-width: 768px) {
	.vivid-blog-wrapper {
		padding-top: 60px;
		padding-bottom: 150px;
	}
}

@media screen and (min-width: 1200px) {
	.vivid-blog-wrapper .col-md-4:nth-child(3n) .vivid-entry {
		float: right;
	}
	
	.vivid-blog-wrapper .col-md-4:nth-child(3n+2) .vivid-entry {
		margin-right: auto;
		margin-left: auto;
	}
}

@media screen and (max-width: 992px) {
	.vivid-post:nth-child(2n+3) {
		clear: both;
	}
}

@media screen and (min-width: 992px) {
	.vivid-post:nth-child(3n+4) {
		clear: both;
	}
}

.vivid-blog-post-wrapper {
	width: 100%;
	position: relative;
	background-color: #F5F5F5;
	padding-top: 30px;
}

@media screen and (min-width: 768px) {
	.vivid-blog-post-wrapper {
		padding-top: 50px;
	}
}

.vivid-entry {
	background: #fff;
	margin-bottom: 50px;
	padding: 0;
	cursor: pointer;
}

@media screen and (min-width: 992px) {
	.vivid-entry .message-entry {
		max-width: 360px;
	}
}

@media screen and (max-width: 768px) {
	.vivid-entry {
		margin-right: 0;
		margin-left: 0;
	}
}

@media screen and (max-width: 1200px) {
	.vivid-entry {
		margin-bottom: 30px;
	}
}

@media screen and (min-width: 1200px) {
	.vivid-entry {
		width: 100%;
	}
}

.vivid-entry:hover h3 {
	text-decoration: underline;
}

.vivid-entry:nth-child(3n+1) {
	clear: both;
}

.vivid-entry-img div {
	background-size: cover;
	background-position: center;
	width: 100%;
	height: 170px;
}

.vivid-entry-info {
	padding: 25px 30px;
	min-height: 210px;
	position: relative;
}

@media screen and (max-width: 768px) {
	.vivid-entry-info {
		padding: 25px;
		min-height: auto;
	}
}

.vivid-entry-info h3 {
	margin-bottom: 9px;
	line-height: inherit;
	font-size: 19px;
	line-height: 25px;
}

.vivid-entry-info p {
	font-size: 13px;
	line-height: 22px;
	color: #2a2a2a;
}

.vivid-entry-info .date {
	position: absolute;
	bottom: 25px;
	right: 35px;
}

.vivid-blog-wrapper + footer,
.vivid-blog-post-wrapper + footer {
	margin-top: 0;
}

.top-menu-wrapper + .vivid-blog-wrapper,
.top-menu-wrapper + .vivid-blog-post-wrapper {
	margin-top: -60px;
}

@media screen and (max-width: 768px) {
	.top-menu-wrapper + .vivid-blog-wrapper,
	.top-menu-wrapper + .vivid-blog-post-wrapper {
		margin-top: -30px;
	}
}

.vivid-blog-post {
	max-width: 830px;
}

@media screen and (min-width: 768px) {
	.vivid-blog-post {
		padding-bottom: 60px;
	}
}

.vivid-blog-top h2 {
	margin-bottom: 0;
}

.vivid-blog-top small {
	margin-bottom: 15px;
	margin-top: -3px;
	display: block;
}

.vivid-blog-top small h5 {
	display: inline-block;
}

.vivid-blog-top .author:after {
	content: '\00b7';
	color: #505559;
	padding: 0 3px;
}

.vivid-blog-top .share-icon {
	font-size: 12px;
	padding-right: 6px;
}

.vivid-blog-content {
	margin-top: 40px;
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	.vivid-blog-content {
		margin-bottom: 30px;
	}
}

.vivid-blog-content .main_image {
	margin-bottom: 60px;
}

@media screen and (max-width: 768px) {
	.vivid-blog-content .main_image {
		margin-bottom: 30px;
	}
}

.vivid-blog-content p,
.vivid-blog-content li {
	color: #2a2a2a;
}

.vivid-blog-content ul li,
.vivid-blog-content ol li {
	padding-bottom: 5px;
}

.vivid-post-tags ul {
	list-style-type: none;
}

.vivid-post-tags li {
	display: inline-block;
}

.vivid-post-tags a {
	padding: 7px 13px;
	background-color: #fff;
	border-radius: 2px;
	margin-right: 6px;
}

@media screen and (min-width: 768px) {
	.vivid-post-share {
		text-align: right;
	}
}

.vivid-post-share .share-icon {
	font-size: 16px;
	padding-left: 10px;
}

.share-title {
	display: inline-block;
}

.vivid-sidemenu {
	margin-top: 20px;
}

@media screen and (min-width: 992px) {
	.vivid-sidemenu {
		margin-top: 0;
	}
}

.vivid-sidemenu p {
	margin-bottom: 10px;
}

.vivid-sidemenu ul {
	list-style-type: none;
	border-left: 1px solid #dddddd;
	padding-left: 20px;
	margin-top: 20px;
	margin-bottom: 0;
	line-height: 24px;
}

.vivid-sidemenu a {
  padding: 7px 0;
  display: block;
  opacity: 0.7;
  font-size: 13px;
  line-height: 20px;
}

.vivid-sidemenu a:hover {
	opacity: 1;
	cursor: pointer;
}

.vivid-sidemenu li.active a {
	font-weight: 500;
	opacity: 1;
}

.vivid-sidemenu li:first-child a {
	padding-top: 0;
}

.vivid-sidemenu li:last-child a {
	padding-bottom: 0;
}

.vivid-sidemenu-latest-posts {
	margin-top: 20px;
}

@media screen and (min-width: 992px) {
	.vivid-sidemenu-latest-posts {
		margin-top: 0;
	}
}

.vivid-sidemenu-latest-posts p {
	margin-bottom: 10px;
}

.vivid-sidemenu-latest-posts ul {
	list-style-type: none;
}

.vivid-sidemenu-latest-posts .latest-posts {
	border-left: 1px solid #dddddd;
	padding-left: 15px;
	margin-bottom: 20px;
	line-height: 24px;
}

.vivid-sidemenu-latest-posts li a {
	padding: 5px 0;
	display: block;
	opacity: 0.7;
	font-size: 13px;
	line-height: 20px;
}

.vivid-sidemenu-latest-posts li a:hover {
	opacity: 1;
	cursor: pointer;
	color: inherit;
}

.vivid-sidemenu-latest-posts h3 {
	border-bottom: 1px solid transparent;
	display: inline-block;
	font-size: 18px;
}

.vivid-sidemenu-latest-posts h3:hover {
	border-bottom: 1px solid;
	opacity: 1;
}

.vivid-sidemenu-latest-posts .active h3 {
	border-bottom: 1px solid;
	display: inline-block;
	opacity: 1;
}

.vivid-sidemenu-latest-posts .active a {
	color: inherit;
}

.vivid-post-navigate {
	background-color: #fff;
	padding: 50px 0;
}

.vivid-post-navigate .icon {
	color: #505559;
	font-size: 20px;
	vertical-align: middle;
}

.vivid-post-navigate .next-arrow {
	padding-left: 10px;
}

.vivid-post-navigate .prev-arrow {
	padding-right: 10px;
}

```