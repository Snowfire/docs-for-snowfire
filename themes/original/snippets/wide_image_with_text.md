The default code for the wide image with text snippet
=====================================================

[More info about this snippet](https://github.com/Snowfire/docs/blob/master/snippets/Theme%20Original/wide_image.md)


```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>My Wide image with text</name>
    <html><![CDATA[

            <div class="content">
                <div class="intro">
                    { com_singlerow(
                        id: '{{ component_id_1 }}',
                        description: 'Headline',
                        htmlElement:'h1'
                    ) }

                    { com_wysiwyg(
                        id: '{{ component_id_2 }}',
                        description: 'Subheading'
                    ) }

                    { com_link(
                        id: '{{ component_id_3 }}',
                        description: 'Button',
                        class: 'button orig'
                    ) }
                </div>
            </div>

            { com_image(
                id: '{{ component_id_0 }}',
                description: 'Image',
                maxWidth: '1920',
                minWidth: '1920',
                maxHeight: '820',
                minHeight: '820',
                html: '
                    <div class="my_wide_image">
                        <div {{ img_parameters | html_decode }} style="height:410px;background-image:url({{ src }})" data-stellar-background-ratio="0.5">
                            <div class="overlay"></div>
                        </div>
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

.columns.my_wide_image_with_text {
  max-width: 100%;
  padding: 0;
}

.column.my_wide_image_with_text {
  position: relative;
}

.column.my_wide_image_with_text .content {
  position: absolute;
  width: 100%;
  z-index: 100;
  pointer-events: none;
}

.column.my_wide_image_with_text .content .intro {
  text-align: center;
  padding: 130px 0;
}

.column.my_wide_image_with_text .content .intro h1 {
  font-size: 32px;
  font-weight: normal;
  margin: 0;
  pointer-events: auto;
}

.column.my_wide_image_with_text .content .intro p {
  color: #fff;
  font-size: 16px;
  opacity: 0.75;
  font-weight: 400;
  pointer-events: auto;
}

.column.my_wide_image_with_text .content .intro p a {
  color: #fff;
  border: 0;
  text-decoration: underline;
}

.column.my_wide_image_with_text .content .intro a {
  pointer-events: auto;
}

.column.my_wide_image_with_text .overlay {
  background: red;
  height: 100%;
  position: absolute;
  width: 100%;
  opacity: 0.7;
}

.snippet_area_main > .my_wide_image_with_text:first-child {
  margin-top: -37px;
}

.snippet_area > .columns.my_wide_image_with_text {
  overflow: visible;
}


```
