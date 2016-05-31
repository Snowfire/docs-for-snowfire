Single row
==========

```xml
{ com_singlerow ( 
	id:'1', 
	description:'Add headline', 
	value:'Hello World' 
) }
```

Parameters
----------

* htmlElement - A singlerow must be wrapped inside an HTML element. If you don't provide this option, Live edit will wrap a <span> around the content. This tag will only exist inside Live edit.
* recommendedMaxLength
* removeHtmlElement - Output just the raw text, without a wrapping html element
* capitalizeFirst - Convert the first letter to upper case and the other to lower case.
* value - Set a default value for the component. Can be used with layout variables, see above example.


Examples
--------

Want to add a h2? 

```xml
{ com_singlerow ( 
	id:'1', 
	description:'Add headline', 
	htmlElement:'h2'
) }
```

This will output the following HTML

```html
<h2>User input</h2>