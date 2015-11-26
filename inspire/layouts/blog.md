# Blog

#### `blog.tpl`

```html
<div class="wrapper" class="{ fnc_designstudio ( part:'header.style' ) }">

    {{ partial: top.tpl }}

    <div id="blog" class="snippet_area_main">

        <div class="container">

                { com_keys (
                    id:'100',
                    description:'Blog posts',
                    class:'post',
                    createButton: 'New post',
                    html:'
                        <article class="posts">
                            <div class="image">
                                <div style="background-image:url({{ keys.image | metaToImage }})"></div>
                            </div>
                            <div class="bg-fade"></div>
                            <div class="col-md-10 col-md-offset-1 relative">
                            <div class="inner inner-posts">
                                <a href="{{ page.url }}" class="act-as-h1">{{ keys.title }}</a>

                                {% if keys.avatar %}
                                <div class="avatar">
                                    <div class="avatar-img" style="background-image:url({{ keys.avatar | metaToImage }})"></div>
                                </div>
                                {% endif %}

                                <div class="text">
                                    {% if keys.author %}
                                    <span class="author">{{ keys.author }}</span>
                                    {% endif %}
                                    <span class="date">{{ page.publishDate | format:"%e %B %Y" }}</span>
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

</div>

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


</snippet_container>
```