# Wysiwyg

```html
<sf-wysiwyg id="{{ component_id }}" description="Enter text"></sf-wysiwyg>
```

## Parameters

* `recommended-max-length` - Defaults to nothing
* `enable-h1` - Boolean, defaults to false
* `enable-lists` - Boolean, defaults to false (enables ul/li)
* `disable-headings` - Boolean, defaults to false
* `strip-tags` - Array, defaults to nothing
* `custom-block-formats` - Array, defaults to nothing. Every item can either be a single HTML element, or a combination of element title and HTML element joined by a pipe. Example: 'code,Pre formated text|pre'
* `value` - Set a default value for the component. Can be used with layout variables.
* `attach-image` - Boolean, defaults to false. If enabled allows the user to add an image to the left/top/right of the text.
* `pToBr` - Boolean, defaults to false. Does not wrap output in a `<p>` and converts linebreaks to `<br>`

## A fully featured example

```html
<sf-wysiwyg
	id="{{ component_id }}"
	description="Enter text here"
	custom-block-format="Quote|blockquote"
	enable-lists="true"
	attach-image="true"
></sf-wysiwyg>
```
