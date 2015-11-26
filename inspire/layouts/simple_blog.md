#Simple blog

###simple_blog.tpl

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

	<div class="appear_as_top_heading_block">
		<div class="content">
			<div class="intro">
				{ com_singlerow(
					id: '199',
					description: 'Headline',
					htmlElement:'h1'
				) }

				{ com_wysiwyg(
					id: '198',
					description: 'Subheading'
				) }
			</div>
		</div>
	</div>

    <div id="simple-blog" class="snippet_area_main">

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
            {% if totalPages > 1 %}
                <div id="pagination">

                    <div class="pages">
                        {% paginate page in pages current: pageNumber limit: 10 %}
                        {% if page == pageNumber %}
                        <span>{{ page }}</span>
                        {% else %}
                        <a href="{{ page | pageNumberToUrl }}">{{ page }}</a>
                        {% endif %}

                        {% endpaginate %}
                    </div>
                </div>
            {% endif %}
            '
        ) }

    </div>

    {{ partial: footer.tpl }}

</div>
```

###simple_blog.xml

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
    
</snippet_container>
```