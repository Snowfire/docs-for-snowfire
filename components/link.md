Image
=====

```xml
{ com_link ( id:'1', description:'Link' ) }
```

Parameters
----------

* linkText - Specify a text that cannot be changed by the user.


Examples
--------

Want to have a clickable h2 element?

```html
<h2>
	{ com_link ( 
		id:'1', 
		description:'Link', 
		class:'button'
	) }
</h2>
```

This will output the following HTML:

```html
<h2><a href="[user_chosen_link]" ckass="button">User input</a></h2>
```