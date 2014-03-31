The default code for the wide image snippet
===========================================

This is almost the same code that generates the snippet "wide_image" which is included by default in Original.
The theme includes Stellar JS which is the lib we use to create the parallax effect. Stellar docs: http://markdalgleish.com/projects/stellar.js/docs/

Please note that you need to change the height on three places in the code below to make it work. The `style: height: 410px` is 50% of the image height and is the actual viewport size of the image.

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
	<name>My Wide image</name>
	<html><![CDATA[

            { com_image(
                id: '{{ component_id_0 }}',
                description: 'Image',
                maxWidth: '1920',
                minWidth: '1920',
                maxHeight: '820',
                minHeight: '820',
                html: '
                    <div class="my_wide_image">
                        <div {{ img_parameters | html_decode }} style="height:410px;background-image:url({{ src }})" data-stellar-background-ratio="0.5"></div>
                    </div>
                '
              )
            }

	]]></html>
</snippet>
```


And add the following CSS code to the global CSS:

```css
/*******************************************
  START CB: My Wide Image
*******************************************/

.columns.my_wide_image,
#blog .columns.my_wide_image {
	max-width: 100%;
	padding: 0;
}

// Column
.column.my_wide_image div {
	background-position: center top;
	background-attachment: fixed;
}

````
