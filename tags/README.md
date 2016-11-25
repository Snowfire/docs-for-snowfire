# Tags

This is a collection of Snowfire Tags that can be used in your code. A Snowfire tag is clickable and opens up some kind of editor (text, upload image etc). 


There are two places to use Snowfire Tags. Inside blocks (create a block in Developer > Code Editor) or in template files. The most popular place is to use them within blocks. This is an example of the image tag inside a block:
```html
{ com_image ( 
    id:          	'{{ component_id }}', 
    description: 	'Image', 
    maxWidth:		'{{ column_width }}'
) }
```

Notice the two variables, `{{ component_id }}` and `{{ column_width }}`. Snowfire will automatically figure out the component_id and the width of the column. You don't need to care about them at all.

If you use a Snowfire tag in a template file, you need to specify them by yourself, example:

```html
{ com_image ( 
    id:          	'1', 
    description: 	'Image', 
    maxWidth:		'400'
) }
```