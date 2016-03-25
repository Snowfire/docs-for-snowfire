Form snippet with a heading
===========================


```xml
<?xml version="1.0" encoding="utf-8"?>
<snippet>
    <name>Form with heading</name>
    <html>
        <![CDATA[

            <div>
                { com_singlerow(id:'{{ component_id }}', description:'Headline', htmlElement:'h1') }
                { com_form(id:'{{ component_id }}', description:'Choose form', disableHeading:'true') }
            </div>

        ]]>
    </html>
</snippet>
```