# Facebook

Add a Facebook feed or like button to the page.


```html
<sf-facebook
    id="{{ component_id_0 }}"
    description="Facebook"
    html-element="div"
    class="facebook"
    width="{{ column_width }}"
>
	<div class="status %type%">
		%photo_large%
		<p>%status% %link_with_ndash%</p>
		<div class="actions">
		    <div class="interaction">
		        <a href="%link_facebook%" target="_blank">%likes_sentence%</a> · <a href="%link_facebook%" target="_blank">%comments_sentence%</a>
		    </div>
		    <div class="author">
		        <a href="%link_facebook%" target="_blank">
		            <span class="name">%name% &ndash;</span>
		            <span class="date">%date_relative%</span>
		         </a>
		    </div>
		</div>
		</div>
</sf-facebook>
```