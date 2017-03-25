# Image

```html
<sf-link id="{{ component_id_0 }}" description="Link"></sf-link>
```

## Parameters

* link-text - Specify a text that cannot be changed by the user.


## Examples

Want to have a clickable h2 element?

```html
<h2>
	<sf-link id="{{ component_id_0 }}" description="Link" class="button"></sf-link>
</h2>
```

This will output the following HTML:

```html
<h2><a href="[user_chosen_link]" class="button">User input</a></h2>
```
