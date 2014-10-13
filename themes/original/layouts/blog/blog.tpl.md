### blog.tpl

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

	<div class="appear_as_top_heading_block">
		<div class="content">
			<div class="intro">
				{ com_singlerow(
					id: '101',
					description: 'Headline',
					htmlElement:'h1'
				) }

				{ com_wysiwyg(
					id: '102',
					description: 'Subheading'
				) }
			</div>
		</div>
	</div>

    <div id="blog" class="snippet_area_main">


        { com_keys (
            id:'100',
            description:'Blog posts',
            class:'post',
            createButton: 'New post',
            html:'

                <article>
                    <header>
	                    <h2><a href="{{ page.url }}">{{ keys.title }}</a></h2>
	                    <small>
		                    {% if keys.author %}
		                    <span class="author">{{ keys.author }}</span>
		                    {% endif %}
		                    <span class="date">{{ page.publishDate | format:"%e %B %Y" }}</span>
	                    </small>
                    </header>
                    <div class="main_image">{{ keys.image }}</div>
                    {{ keys.text }}
                </article>',
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