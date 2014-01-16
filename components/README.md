Components
==========

This is a collection of components that can be used in Snowfire. A component is clickable and opens up some kind of editor (text, upload image etc). 

There are two places to use components. Inside snippets (create a snippet in Developer > Code Editor) or in Layout files. The most popular place is to use them within snippets. This is an example of the image component inside a snippet:

```html
{ com_image ( 
    id:          	'{{ component_id }}', 
    description: 	'Image', 
    maxWidth:		'{{ column_width }}'
) }
```

Notice the two variables, `{{ component_id }}` and `{{ column_width }}`. Snowfire will automatically figure out the component_id and the width of the column. You don't need to care about them at all.

If you use a component in a Layout file, you need to specify them by yourself, example:

```html
{ com_image ( 
    id:          	'1', 
    description: 	'Image', 
    maxWidth:		'400'
) }
```