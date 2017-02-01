# Single row

```
<sf-singlerow
	id="{{ component_id }}"
	description="Add title"
	html-element="h1"
></sf-singlerow>
```

## Parameters

* `html-element` - A singlerow must be wrapped inside an HTML element. If you don't provide this option, Live edit will wrap a <span> around the content. This tag will only exist inside Live edit.
* `recommended-max-length`
* `remove-html-element` - Output just the raw text, without a wrapping html element
* `capitalize-first` - Convert the first letter to upper case and the other to lower case
* `value` - Set a default value for the component. Can be used with template variables

## Example

The code above outputs

```html
<h1>User input</h1>
```