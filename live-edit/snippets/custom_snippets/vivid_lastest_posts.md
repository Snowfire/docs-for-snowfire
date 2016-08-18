#Vivid latest posts

This block picks the three latest blog posts from the blog. The style is the same as vivid blog.

###HTML

```html
<div class="row">
	<div class="vivid-latest-post-wrapper">
		{ com_keys (
            id:'197',
            description:'Blog posts',
            class:'col-sm-6 col-md-4 vivid-post',
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
            useChildPages: 'false',
            perPage: '3',
            offset: '0',
            paginationHtml:'
            <div class="clearfix"></div>
            
            '
        ) }
    </div>
</div>
```

###CSS

```css 
@media screen and (max-width: 769px) {
	.vivid-latest-post-wrapper .vivid-entry {
	    margin-bottom: 30px;
	}
}

.vivid-latest-post-wrapper .vivid-entry {
    background: #f5f5f5;
    margin-bottom: 0;
} 
```
