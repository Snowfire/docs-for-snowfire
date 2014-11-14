Image2
=====

```xml
{ com_image2 (
  id:'{{ component_id }}', 
  description:'image', 
  autoWidth:'true', 
  dimensions:'max'
) }
```

Parameters
----------

* html
* width
* height
* autoWidth (boolean)
* dimensions
* placeholderWidth
* linkable (boolean)
* resizable (boolean)


### html

Uses a Snowfire flavor of the Liquid template language.

Variables available are: 
* src
* attributes_html – e.g. `alt="" class="classes"`
* alt


### autoWidth

Automatically set width by parent element.


### dimensions

* `max` – Use width and height as max size
* `min` – Use width and height as min size
