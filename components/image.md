Image
=====

```xml
{ com_image ( 
    id:          	'1', 
    description: 	'Image', 
    maxHeight:   	'300',
    linkable:    	'true'
) }
```

Parameters
----------

* maxWidth
* maxHeight
* linkable - boolean.
* crop - boolean.
* altAsLinkTitle - boolean.
* linkClass - class on <a> tag. Deprecated, use a-class instead.
* canHaveEmptyLink - By default the <a> tag is stripped out if no link was selected by the user.
* enableVideo - boolean.
* autoLinkToFile - boolean. Will automatically link the image to the original image file. _Requires linkable:'true'_
* placeholderHeight - Specific width/height for the place holder image
* placeholderWidth - Specific width/height for the place holder image