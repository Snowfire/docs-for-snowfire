# Tags

This is a collection of Snowfire Tags that can be used in your code. A Snowfire tag is clickable and opens up some kind of editor (text, upload image etc). 


There are two places to use Snowfire Tags. Inside blocks (create a block in Developer > Code Editor) or in template files. The most popular place is to use them within blocks. This is an example of the image tag inside a block:
```html
<sf-image2 id="{{ component_id }}" description="Image" width="{{ column_width }}"></sf-image2>
```

Notice the two variables, `{{ component_id }}` and `{{ column_width }}`. Snowfire will automatically figure out the component_id and the width of the column. You don't need to care about them at all.

If you use a Snowfire tag in a template file, you need to specify them by yourself, example:

```html
<sf-image2 id="1" description="Image" width="400"></sf-image2>
```

## Sync block content across pages

If you are creating a footer partial with tags you can use sync-id on your tags. This will make sure the content sync across all pages where this tag is, example:

```html
<sf-wysiwyg id="100" description="Text" sync-id="100"></sf-wysiwyg>
```

We recommend using the same `id` and `sync-id` but this is only a recommendation. If you want to know which sync ids is available, use the DEV-dropdown.