Intro snippet
=============

Create a snippet named "intro" with the following code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Intro</name>
    <html>
        <![CDATA[

            <div class="intro_top">
                <div class="intro_icon">
                    { com_image(
                        id: '{{ component_id }}',
                        description: 'Image',
                        maxHeight: '40',
                        maxWidth: '40',
                        crop: 'true'
                    )}
                </div>
                <div class="intro_heading">
                    { com_singlerow(id:'{{ component_id }}', description:'Heading') }
                </div>
            </div>

            <div class="intro_content">
                { com_wysiwyg(id:'{{ component_id }}', description:'Text') }
            </div>

        ]]>
    </html>
</snippet>
```

Add the following code the global CSS:

```css
/*******************************************
	START CB: INTRO  
*******************************************/

.column.intro .intro_top .intro_icon {
  float: left;
  margin-right: 10px;
}
.column.intro .intro_top .intro_icon img {
  border-radius: 40px;
}
.column.intro .intro_top .intro_heading {
  line-height: 44px;
  font-weight: bold;
  margin-bottom: 14px;
}
.column.intro .intro_content {
  clear: both;
}


/*******************************************
	END CB: INTRO  
*******************************************/
```
