Feature snippet
===============

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


And add the following CSS code to the global CSS:

```css
/*******************************************
    START CB: FEATURE
*******************************************/
.columns.feature {
  position: relative;
}


.column.feature .flexslider ul {
  margin: 0;
  padding: 0;
  list-style-type: none;
}

.column.feature .feature_intro {
  position: absolute;
  top: 10px;
  left: 10px;
  right: 10px;
}

.column.feature .feature_intro .call_to_action {
  margin-bottom: 10px;
}

.column.feature .call_to_action a {
  border: none;
  color: #FFF;
  cursor: pointer;
  height: 34px;
  float: left;
  border-radius: 3px;
  background-color: #2BA6CB;
  padding: 9px 16px;
  letter-spacing: 0.08em;
}
@media only screen and (max-width: 767px) {
  .column.feature .feature_intro {
    position: static;
  }
  .column.feature img {
    margin-bottom: 10px;
  }
  .column.feature .call_to_action {
    margin-bottom: 20px;
  }
}
/*******************************************
    END CB: FEATURE
*******************************************/
````