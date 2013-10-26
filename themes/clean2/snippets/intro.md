Intro snippet
=============

Create a snippet with the following code:

```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Feature</name>
    <html><![CDATA[
        <div class="flexslider">
            { com_imagecollection (
                    id: '{{ component_id }}',
                    description: 'Add image',
                    htmlElement: 'ul',
                    class: 'slides',
                    width: '{{ column_width }}',
                    height: '400',
                    placeholderHeight:'200'
                    crop: 'true',
                    itemHtml: '
                        <li>%image%</li>
                    '
            ) }
        </div>
		<div class="feature_intro">
		    { com_wysiwyg(id:'{{ component_id }}', description:'Text') }
		    <div class="call_to_action">{ com_link(id:'{{ component_id }}', description:'Button') }</div>
		</div>
	]]></html>
</snippet>
```

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