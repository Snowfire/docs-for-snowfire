Wysiwyg
=====

```xml
{ com_wysiwyg ( id:'1', description:'Enter text' ) }
```

Parameters
----------

* recommendedMaxLength - Defaults to nothing
* enableH1 - Boolean, defaults to false
* enableLists - Boolean, defaults to false (enables ul/li)
* disableHeadings - Boolean, defaults to false
* stripTags - Array, defaults to nothing
* customBlockformats - Array, defaults to nothing. Every item can either be a single HTML element, or a combination of element title and HTML element joined by a pipe. Example: 'code,Pre formated text|pre'
* value - Set a default value for the component. Can be used with layout variables.
* attachImage - Boolean, defaults to false. If enabled allows the user to add an image to the left/top/right of the text.
* pToBr - Boolean, defaults to false. Does not wrap output in a `<p>` and converts linebreaks to `<br>`


A fully featured example
------------------------


```html
{ com_wysiwyg (
	id: '1', 
	description: 'Enter text here', 
	customBlockformats: 'Quote|blockquote', 
	enableLists: 'true',
	attachImage:'true'
) }
```
