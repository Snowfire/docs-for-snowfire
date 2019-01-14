# Snowfire template engine

The template engine is our way to give you even more power to create exactly the page you want. When using the engine you get access to data from the database and can apply logic. 

### Example

```html
<ul>
    [% for tag in tags('limit: 5') %]
        <li>
        	[[ tag.name ]]
        </li>
    [% endfor %]
</ul>
```

This code retrieves 5 tags from the database and displays them in a ul/li list. You are in control of everything.

### Behind the scenes

Snowfire template engine is based on [Twig](http://twig.sensiolabs.org/) and you can apply basic filters like: `[[ tag.name | upper ]]` to make the tag name in upper case. You could also do something like this:

```html
[% for tag in childrenTags('limit: 5') %]
	<div>
		[% if (tag.name == 'special') %]
			<div>This tag is special</div>
		[% else %]
			<div>This tag is not special at all :/</div>
		[% endif %]
	</div>
[% endfor %]
```

I hope this give you a feel of what can be done. Please look deeper into the docs to see which methods are available, what data you can get and which filters you can apply. 
