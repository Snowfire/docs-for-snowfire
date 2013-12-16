Liquid
======

```xml
{ com_liquid ( id:'1', description:'Enter text', code:'' ) }
```


List all tags
-------------


```html
{ com_liquid ( id:'1', description:'Groups', code:'
	{% if page.children.tags != empty %}
		{% for tag in page.children.tags exclude:keys.tagsFilter %}
			<li><a href="{{ tag | tagToUrl:page }}">{{ tag }}</a></li>
		{% endfor %}
	{% endif %}
' ) }
```


Create a list of year/months for blog posts
-------------------------------------------


```html
{ com_liquid ( id:'1', description:'Archive', code:'
	<ul>
		{% grouped year in selectedPage.children by:"publish date" groups:"%Y|%B"  %}
			<li>
				<h4>{{ year }}</h4>

				<ul>
					{% for month in year %}
						<li><a href="blog/date:{{ year }}-{{ month | monthToNumeric }}">{{ month | capitalize }}</a></li>
					{% endfor %}
				</ul>
			</li>
		{% endgrouped %}
	</ul>
' ) }
```