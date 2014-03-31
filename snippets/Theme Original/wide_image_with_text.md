The default code for the wide image with text snippet
=====================================================



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
                maxHeight: '615',
                minHeight: '615',
                html: '
                    <div class="wide_image">
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

.column.my_wide_image_with_text .content {
  position: absolute;
  width: 100%;
}

.column.my_wide_image_with_text .content .intro {
  text-align: center;
  padding: 5em 0;
}

.column.my_wide_image_with_text .content .intro h1 {
  font-size: 32px;
  color: #fff;
  font-weight: normal;
  margin: 0;
}

.column.my_wide_image_with_text .content .intro p {
  color: #fff;
  font-size: 16px;
  opacity: 0.75;
  font-weight: 400;
}

.snippet_area_main > .my_wide_image_with_text:first-child {
  margin-top: -37px;
}


```
