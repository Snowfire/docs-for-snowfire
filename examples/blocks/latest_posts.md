# Latest post

```html
<div class="latest_posts">
    <ul>
        <sf-keys
            id="1"
            description="Latest posts"
            html-element="li"
            limit="10"
            sort-by="publishedDate descending"
        >
            <a href="{{ page.url }}">{{ keys.title }}</a>
        </sf-keys>
    </ul>
</div>
```
